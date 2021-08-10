# 主流程脚本 `src/main.py`

- 准备
    - 检测二进制文件 `check_bin()`
    - 解析参数 `parse_option()`
    - 设置输出目录 `setup_output_dir()`
    - 设置日志 `setup_logger()`
    - 检查并修正参数 `check_and_correct_option()`
    - 检查reads类型 `check_reads()`
    - cpu调度 `cpu_dispatch()`
- 预处理
    - 创建目录 `create_library_file()`
    - 建库 `build_library()`
    - 设置`max_k`
- 组装
    - 建第一个图 `build_first_graph()`
    - `k = kmin`整体组装 `assemble(opt.k_min)`
    - `k = next_k, k <= kmax`多次kmer组装
        - 局部组装 `local_assemble()`
        - 建图 `build_graph()`
        - 整体组装 `assemble()`
    - 合并结果输出最终重叠群`merge_final()`

## python脚本与c++主程序交互
- python生成cmd命令
- subprocess.Popen通过cmd命令调用可执行文件
 ```python
 def run_sub_command(cmd, msg, verbose=False):
    ...

    p = subprocess.Popen(cmd, stderr=subprocess.PIPE)

    ...
 ```



