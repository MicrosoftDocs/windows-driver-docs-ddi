---
UID: NS:d3dumddi.D3DDDICB_LOGUMDMARKER
title: D3DDDICB_LOGUMDMARKER (d3dumddi.h)
description: Specifies info about the location of an Event Tracing for Windows (ETW) marker event that the user-mode display driver has defined.
old-location: display\d3dddicb_logumdmarker.htm
tech.root: display
ms.assetid: D953C714-6C11-4F8A-A7F9-416A00C518B4
ms.date: 05/10/2018
keywords: ["D3DDDICB_LOGUMDMARKER structure"]
ms.keywords: D3DDDICB_LOGUMDMARKER, D3DDDICB_LOGUMDMARKER structure [Display Devices], d3dumddi/D3DDDICB_LOGUMDMARKER, display.d3dddicb_logumdmarker
req.header: d3dumddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
req.typenames: D3DDDICB_LOGUMDMARKER
f1_keywords:
 - D3DDDICB_LOGUMDMARKER
 - d3dumddi/D3DDDICB_LOGUMDMARKER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3dumddi.h
api_name:
 - D3DDDICB_LOGUMDMARKER
---

# D3DDDICB_LOGUMDMARKER structure


## -description

Specifies info about the location of an Event Tracing for Windows (ETW) marker event that the user-mode display driver has defined.

## -struct-fields

### -field hContext

[in] A handle to a Direct3D context that signals ETW marker events. This is also the context that the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_rendercb">pfnRenderCb</a> function will be called on.

### -field APISequenceNumber

The API sequence number that the marker event is associated with.

### -field Index

Indicates which API sequence call caused this marker event. If zero, the marker event corresponds to the latest API sequence number after a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_setmarker">pfnSetMarker</a> function. If 1, the marker event is located at the following API sequence number. And so on.

Should be -1 if no time stamps are associated with this marker event.

### -field StringIndex

The offset, in bytes, of the string table entry pointed to by <b>Info</b>. Can be negative if the string is passed along with the marker event.

### -field Info

A custom text string embedded in the ETW packet. Can be <b>NULL</b>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_rendercb">pfnRenderCb</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_setmarker">pfnSetMarker</a>

