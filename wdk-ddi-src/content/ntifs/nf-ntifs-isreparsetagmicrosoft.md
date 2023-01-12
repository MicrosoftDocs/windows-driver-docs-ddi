---
UID: NF:ntifs.IsReparseTagMicrosoft
title: IsReparseTagMicrosoft macro (ntifs.h)
description: The IsReparseTagMicrosoft macro determines whether a reparse point tag indicates a Microsoft reparse point.
old-location: ifsk\isreparsetagmicrosoft.htm
tech.root: ifsk
ms.date: 07/26/2022
keywords: ["IsReparseTagMicrosoft macro"]
ms.keywords: IsReparseTagMicrosoft, IsReparseTagMicrosoft function [Installable File System Drivers], ifsk.isreparsetagmicrosoft, ioref_ef573233-e933-490e-b762-1ce20343c65c.xml, ntifs/IsReparseTagMicrosoft
req.header: ntifs.h
req.include-header: Ntifs.h
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
req.irql: Any level
targetos: Windows
req.typenames: 
f1_keywords:
 - IsReparseTagMicrosoft
 - ntifs/IsReparseTagMicrosoft
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - IsReparseTagMicrosoft
---

# IsReparseTagMicrosoft macro

## -description

The **IsReparseTagMicrosoft** macro determines whether a reparse point tag indicates a Microsoft reparse point.

## -parameters

### -param _tag [in]

Reparse point tag to be tested.

## -remarks

Only Microsoft reparse points can use Microsoft tags. Third-party reparse points must use non-Microsoft tags. However, third-party drivers can set Microsoft reparse points. For more information, see the Remarks section of the reference entry for the [**REPARSE_GUID_DATA_BUFFER**](ns-ntifs-_reparse_guid_data_buffer.md) structure.

For more information about reparse points, see the Microsoft Windows SDK documentation.

## -see-also

[**FSCTL_DELETE_REPARSE_POINT**](/windows-hardware/drivers/ifs/fsctl-delete-reparse-point)

[**FSCTL_GET_REPARSE_POINT**](/windows-hardware/drivers/ifs/fsctl-get-reparse-point)

[**FSCTL_SET_REPARSE_POINT**](/windows-hardware/drivers/ifs/fsctl-set-reparse-point)

[**FltFsControlFile**](../fltkernel/nf-fltkernel-fltfscontrolfile.md)

[**FltTagFile**](../fltkernel/nf-fltkernel-flttagfile.md)

[**FltUntagFile**](../fltkernel/nf-fltkernel-fltuntagfile.md)

[**IsReparseTagNameSurrogate**](nf-ntifs-isreparsetagnamesurrogate.md)

[**REPARSE_DATA_BUFFER**](ns-ntifs-_reparse_data_buffer.md)

[**REPARSE_GUID_DATA_BUFFER**](ns-ntifs-_reparse_guid_data_buffer.md)

[**ZwFsControlFile**](nf-ntifs-zwfscontrolfile.md)
