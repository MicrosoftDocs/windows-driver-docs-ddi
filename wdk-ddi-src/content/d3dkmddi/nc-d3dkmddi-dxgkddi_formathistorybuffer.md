---
UID: NC:d3dkmddi.DXGKDDI_FORMATHISTORYBUFFER
title: DXGKDDI_FORMATHISTORYBUFFER (d3dkmddi.h)
description: Copies unformatted data from the history buffer into a buffer that's properly formatted to be submitted to the Event Tracing for Windows (ETW) facility.
old-location: display\dxgkddiformathistorybuffer.htm
ms.assetid: 84417629-5C12-4CB5-B147-0A558A4F9090
ms.date: 05/10/2018
ms.keywords: DXGKDDI_FORMATHISTORYBUFFER, DXGKDDI_FORMATHISTORYBUFFER callback, DxgkDdiFormatHistoryBuffer, DxgkDdiFormatHistoryBuffer callback function [Display Devices], d3dkmddi/DxgkDdiFormatHistoryBuffer, display.dxgkddiformathistorybuffer
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1,WDDM 1.3
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
req.irql: DISPATCH_LEVEL
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - "d3dkmddi/DxgkDdiFormatHistoryBuffer"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3dkmddi.h
api_name:
 - DxgkDdiFormatHistoryBuffer
product:
 - Windows
---

# DXGKDDI_FORMATHISTORYBUFFER callback function

## -description

 Copies unformatted data from the history buffer into a buffer that's properly formatted to be submitted to the Event Tracing for Windows (ETW) facility.

## -parameters

### -param hContext

A handle to the device context for the DMA buffer that contains the unformatted history buffer.

### -param pFormatData

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_formathistorybuffer">DXGKARG_FORMATHISTORYBUFFER</a> structure that contains data about how to format the history buffer.

## -returns

Returns <b>STATUS_SUCCESS</b> if it succeeds; otherwise, it returns one of the error codes defined in Ntstatus.h.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_formathistorybuffer">DXGKARG_FORMATHISTORYBUFFER</a>

