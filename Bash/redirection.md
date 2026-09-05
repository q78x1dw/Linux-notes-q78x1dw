## User

imply bash's redirection grammar briefly

## DeepSeek

Bash 重定向的核心语法围绕 **文件描述符（File Descriptor, FD）** 展开：

- **0** = 标准输入 (stdin)
- **1** = 标准输出 (stdout)
- **2** = 标准错误 (stderr)

语法公式：`[n] 操作符 [目标]`（`n` 省略时默认为 1 或 0）。

---

### 1. 核心操作符速查

| 操作符 | 含义 | 实例 |
| :--- | :--- | :--- |
| **`>`** | 覆盖写入（标准输出） | `ls > list.txt` |
| **`>>`** | 追加写入 | `echo "new" >> log.txt` |
| **`<`** | 从文件读入（标准输入） | `wc -l < data.txt` |
| **`2>`** | 覆盖写入错误输出 | `find / -name "x" 2> err.log` |
| **`2>>`** | 追加写入错误输出 | `cmd 2>> err.log` |
| **`&>`** | **合并**重定向（即 `>` 相当于 `1>`，`&>` 把 1 和 2 全写进去） | `cmd &> all.log` |
| **`2>&1`** | 将错误输出**复制**到标准输出的位置（合并） | `cmd > all.log 2>&1` |
| **`|`** | 管道（前一个 stdout 给后一个 stdin） | `grep "a" file \| wc -l` |
| **`<<`** | Here Document（内联多行输入） | `cat << EOF`（直到遇到 EOF） |
| **`<<<`** | Here String（字符串作为输入） | `bc <<< "2+3"` |

---

### 2. 最危险的陷阱：顺序至关重要！

`2>&1` 必须写在**目标文件之后**，否则会丢失错误信息：

- **正确**：`cmd > file 2>&1` （先把 stdout 指向 file，再把 stderr 指向 stdout 的位置，二者全进 file）
- **错误**：`cmd 2>&1 > file` （先把 stderr 指向终端 stdout，再把 stdout 指向 file，结果 stderr 依然打在屏幕上）

---

### 3. 快速扔掉（丢黑洞）
- `cmd 2>/dev/null` （只屏蔽报错）
- `cmd &>/dev/null` （全部静默，不输出任何信息）

一句话总结：**`>` 管正常输出，`2>` 管报错，`&>` 或 `2>&1` 合一起，顺序别搞反。**
