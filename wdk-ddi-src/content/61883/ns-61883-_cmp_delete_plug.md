---
UID: NS:61883._CMP_DELETE_PLUG
title: _CMP_DELETE_PLUG (61883.h)
description: This structure is used to delete a plug.Av61883_CreatePlug.
old-location: ieee\cmp_delete_plug.htm
tech.root: IEEE
ms.date: 02/15/2018
keywords: ["CMP_DELETE_PLUG structure"]
ms.keywords: "*PCMP_DELETE_PLUG, 61883/CMP_DELETE_PLUG, 61883/PCMP_DELETE_PLUG, CMP_DELETE_PLUG, CMP_DELETE_PLUG structure [Buses], IEEE.cmp_delete_plug, PCMP_DELETE_PLUG, PCMP_DELETE_PLUG structure pointer [Buses], _CMP_DELETE_PLUG"
req.header: 61883.h
req.include-header: 
req.target-type: Windows
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
req.typenames: CMP_DELETE_PLUG, *PCMP_DELETE_PLUG
f1_keywords:
 - _CMP_DELETE_PLUG
 - 61883/_CMP_DELETE_PLUG
 - PCMP_DELETE_PLUG
 - 61883/PCMP_DELETE_PLUG
 - CMP_DELETE_PLUG
 - 61883/CMP_DELETE_PLUG
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - 61883.h
api_name:
 - _CMP_DELETE_PLUG
 - PCMP_DELETE_PLUG
 - CMP_DELETE_PLUG
---

# _CMP_DELETE_PLUG structure


## -description

This structure is used to delete a plug.The request deletes a plug control register (iPCR or oPCR) that was created with <a href="https://msdn.microsoft.com/library/windows/hardware/ff536961">Av61883_CreatePlug</a>. A driver is responsible for deleting all of the plugs it has created before the system unloads the driver.

## -struct-fields

### -field hPlug

On input, a handle to the plug to delete.

## -remarks

If successful, the IEC-61883 protocol driver sets <b>Irp->IoStatus.Status </b>to STATUS_SUCCESS.

## -see-also

<a href="/windows-hardware/drivers/ddi/61883/ns-61883-_av_61883_request">AV_61883_REQUEST</a>

