# NPOI



## 基础介绍

一个强大的 .NET 库，用于读取、写入以及处理 Microsoft Excel 文件，支持 .xls 和 .xlsx 格式
还支持其他 Microsoft Office 文件格式（如 Word、PowerPoint）
`Install-Package NPOI`



## 核心内容
```yaml
NPOI:
    XSSF:
        UserModel:
            HSSFCell:
                CellStyle:
                SetCellFormula():
                SetCellValue():
            HSSFCellStyle:
            HSSFDataFormat:
            HSSFFormulaEvaluator:
            HSSFFont:
            HSSFRow:
                CreateCell():
                GetCell():
            HSSFSheet:
                LastRowNum:
                CreateRow():
                GetRow():
            XSSFWorkbook:
                CreateSheet():
                GetSheetAt():
```