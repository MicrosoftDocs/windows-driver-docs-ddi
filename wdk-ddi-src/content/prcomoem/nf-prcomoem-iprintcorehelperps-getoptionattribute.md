---
UID: NF:prcomoem.IPrintCoreHelperPS.GetOptionAttribute
title: IPrintCoreHelperPS::GetOptionAttribute (prcomoem.h)
description: The IPrintCoreHelperPS::GetOptionAttribute method retrieves the option attribute list or the value of a specific option attribute.
tech.root: print
ms.date: 07/25/2022
keywords: ["IPrintCoreHelperPS::GetOptionAttribute"]
ms.keywords: GetOptionAttribute, GetOptionAttribute method [Print Devices], GetOptionAttribute method [Print Devices],IPrintCoreHelperPS interface, IPrintCoreHelperPS interface [Print Devices],GetOptionAttribute method, IPrintCoreHelperPS.GetOptionAttribute, IPrintCoreHelperPS::GetOptionAttribute, prcomoem/IPrintCoreHelperPS::GetOptionAttribute, print.iprintcorehelperps_getoptionattribute, print_unidrv-pscript_allplugins_9c895bf8-2a17-4a3a-b97d-e747f5996318.xml
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
 - IPrintCoreHelperPS::GetOptionAttribute
 - prcomoem/IPrintCoreHelperPS::GetOptionAttribute
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - prcomoem.h
api_name:
 - IPrintCoreHelperPS::GetOptionAttribute
---

## -description

The **IPrintCoreHelperPS::GetOptionAttribute** method retrieves the option attribute list or the value of a specific option attribute.

## -parameters

### -param pszFeatureKeyword [in]

A pointer to a caller-supplied buffer that contains an ANSI string that specifies the feature keyword to query for.

### -param pszOptionKeyword [in]

A pointer to a caller-supplied buffer that contains an ANSI string that specifies the option keyword to query for. This value can be obtained from a prior call to [IPrintCoreHelperPS::EnumOptions](./nf-prcomoem-iprintcorehelperps-enumoptions.md).

### -param pszAttribute [in]

A pointer to a caller-supplied buffer that contains an ANSI string that specifies the attribute requested. If this parameter is **NULL**, the caller is requesting a list of all supported attribute names for the option instead of specifying a specific attribute name for the option.

### -param pdwDataType [out]

A pointer to a variable that receives a value that specifies the data type of the requested attribute. This value is an enumerator of the [EATTRIBUTE_DATATYPE](../printoem/ne-printoem-_eattribute_datatype.md) enumeration type, which is defined in printoem.h.

### -param ppbData [out]

A pointer to a callee-allocated buffer containing the requested data. Upon completion of this method, the caller does not need to release this buffer.

### -param pcbSize [out]

A pointer to a variable that receives the size, in bytes, of the buffer that is pointed to by the *pbData* parameter.

## -returns

**IPrintCoreHelperPS::GetOptionAttribute** should return one of the following values.

| Return code | Description |
|--|--|
| **S_OK** | The method succeeded. |
| **E_FAIL** | The method failed. |
| **E_INVALIDARG** | The method attempted to query for a nonexistent attribute. This value might also mean that the feature keyword name or option keyword name were not recognized. |
| **E_OUTOFMEMORY** | The value in *pcbSize* was smaller than the number of bytes to be written to the output buffer that is pointed to by *pbData*. |

## -remarks

If **IPrintCoreHelperPS::GetOptionAttribute**is called with its *pszAttribute* and *pbData* parameters set to **NULL**, the method returns with *pcbSize* set to the number of bytes that are needed for the list of all of the supported attribute names for the option. If this method is called a second time, with *pszAttribute* set to **NULL** and *pbData* pointing to a buffer of the size that was specified in *pcbSize* in the previous call, the method returns with *pdwDataType* set to kADT_ASCII (an enumerator of the [EATTRIBUTE_DATATYPE](../printoem/ne-printoem-_eattribute_datatype.md) enumeration type) and *pbData* pointing to a NULL-delimited list of all of the supported attribute names for the option. This list is terminated with two null characters.

For more information about **IPrintCoreHelperPS::GetOptionAttribute**, see [Using GetOptionAttribute](/windows-hardware/drivers/print/using-getoptionattribute).

## -see-also

[IPrintCoreHelperPS](./nn-prcomoem-iprintcorehelperps.md)

[IPrintCoreHelperPS::GetFeatureAttribute](./nf-prcomoem-iprintcorehelperps-getfeatureattribute.md)

[IPrintCoreHelperPS::GetGlobalAttribute](./nf-prcomoem-iprintcorehelperps-getglobalattribute.md)