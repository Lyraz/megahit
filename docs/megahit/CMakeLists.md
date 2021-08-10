# CMakeLists

## 源码结构
```text
.
└── src
     ├── main.py / main.cpp / main_assemble.cpp ...
     ├── sdbg
           ├── ...
     ├── assembly
           ├── ...
     ├── localasm
           ├── ...
     ├──

```

## 基本信息
- Project: megahit
- Version: >= 2.8
- Standard: c++11

## 参数选项
- COVERAGE: OFF
- STATIC_BUILD: OFF
- SANITIZER: OFF
- TSAN: OFF

## 源码目录
- OTHER_SOURCE `src/main*.cpp, src/utils/options_description.cpp`
- ASMBL_SOURCE `src/assembly/*.cpp`
- LCASM_SOURCE `src/localasm/*.cpp`
- IDBA_SOURCE `src/idba/*.cpp`
- SDBG_SOURCE `src/sdbg/*.cpp`
- CX1_SOURCE `src/sorting/*.cpp`
- SEQ_SOURCE `src/sequence/*.cpp`
- TOOLKIT_SOURCE `src/tools/*.cpp`

## 生成目标可执行文件
- megahit_core(cpu支持bmi2和popcnt)
    - 源文件: `${OTHER_SOURCE} ${ASMBL_SOURCE} ${IDBA_SOURCE} ${SDBG_SOURCE} ${LCASM_SOURCE} ${SEQ_SOURCE} ${CX1_SOURCE} ${TOOLKIT_SOURCE}`
    - 条件编译: `-mbmi2 -DUSE_BMI2 -mpopcnt`
- megahit_core_popcnt(cpu支持popcnt)
    - 源文件: `${OTHER_SOURCE} ${ASMBL_SOURCE} ${IDBA_SOURCE} ${SDBG_SOURCE} ${LCASM_SOURCE} ${SEQ_SOURCE} ${CX1_SOURCE} ${TOOLKIT_SOURCE}`
    - 条件编译: `-mpopcnt`
- megahit_core_no_hw_accel
    - 源文件: `${OTHER_SOURCE} ${ASMBL_SOURCE} ${IDBA_SOURCE} ${SDBG_SOURCE} ${LCASM_SOURCE} ${SEQ_SOURCE} ${CX1_SOURCE} ${TOOLKIT_SOURCE}`

