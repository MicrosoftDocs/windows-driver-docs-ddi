---
UID: NF:prcomoem.IPrintCoreHelperPS.GetGlobalAttribute
title: IPrintCoreHelperPS::GetGlobalAttribute (prcomoem.h)
description: The IPrintCoreHelperPS::GetGlobalAttribute method retrieves the global attribute list or the value of a specific global attribute.
tech.root: print
ms.date: 07/25/2022
keywords: ["IPrintCoreHelperPS::GetGlobalAttribute"]
ms.keywords: GetGlobalAttribute, GetGlobalAttribute method [Print Devices], GetGlobalAttribute method [Print Devices],IPrintCoreHelperPS interface, IPrintCoreHelperPS interface [Print Devices],GetGlobalAttribute method, IPrintCoreHelperPS.GetGlobalAttribute, IPrintCoreHelperPS::GetGlobalAttribute, prcomoem/IPrintCoreHelperPS::GetGlobalAttribute, print.iprintcorehelperps_getglobalattribute, print_unidrv-pscript_allplugins_9c11e4ae-21bd-493c-b4d0-39b8406c8843.xml
req.header: prcomoem.h
req.include-header: Prcomoem.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - IPrintCoreHelperPS::GetGlobalAttribute
 - prcomoem/IPrintCoreHelperPS::GetGlobalAttribute
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - prcomoem.h
api_name:
 - IPrintCoreHelperPS::GetGlobalAttribute
---

## -description

The **IPrintCoreHelperPS::GetGlobalAttribute** method retrieves the global attribute list or the value of a specific global attribute.

## -parameters

### -param pszAttribute [in]

A pointer to a caller-supplied buffer that contains an ANSI string that specifies the requested attribute. If this parameter is **NULL**, the caller is requesting a list of all of the supported global attribute names instead of specifying a specific global attribute name.

### -param pdwDataType [out]

A pointer to variable that receives a value that specifies the data type of the requested attribute. This value is an enumerator of the [EATTRIBUTE_DATATYPE](/windows-hardware/drivers/ddi/printoem/ne-printoem-_eattribute_datatype) enumeration type, which is defined in printoem.h.

### -param ppbData [out]

A pointer to a callee-allocated buffer containing the requested data. Upon completion of this method, the caller does not need to release this buffer.

### -param pcbSize [out]

A pointer to a variable that specifies the size, in bytes, of the buffer that is pointed to by the *pbData* parameter.

## -returns

**IPrintCoreHelperPS::GetGlobalAttribute** should return one of the following values.

| Return code | Description |
|--|--|
| **S_OK** | The method succeeded. |
| **E_FAIL** | The method failed. |
| **E_INVALIDARG** | The method attempted to query for a nonexistent attribute. |
| **E_OUTOFMEMORY** | The value in *pcbSize* was smaller than the number of bytes to be written to the output buffer that is pointed to by *pbData*. |

## -remarks

If **IPrintCoreHelperPS::GetGlobalAttribute** is called with its *pszAttribute* and *pbData* parameters set to **NULL**, the method returns with *pcbSize* set to the number of bytes that are needed for the list of all of the supported global attribute names. If this method is called a second time, with *pszAttribute* set to **NULL** and *pbData* pointing to a buffer of the size that was specified in *pcbSize* in the previous call, the method returns with *pdwDataType* set to kADT_ASCII (an enumerator of the [EATTRIBUTE_DATATYPE](/windows-hardware/drivers/ddi/printoem/ne-printoem-_eattribute_datatype) enumeration type) and *pbData* pointing to a NULL-delimited list of all of the supported global attribute names. This list is terminated with two null characters.

For more information about **IPrintCoreHelperPS::GetGlobalAttribute**, see [Using GetGlobalAttribute](/windows-hardware/drivers/print/using-getglobalattribute).

## -see-also

[IPrintCoreHelperPS](/windows-hardware/drivers/ddi/prcomoem/nn-prcomoem-iprintcorehelperps)

[IPrintCoreHelperPS::GetFeatureAttribute](/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintcorehelperps-getfeatureattribute)

[IPrintCoreHelperPS::GetOptionAttribute](/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintcorehelperps-getoptionattribute)
