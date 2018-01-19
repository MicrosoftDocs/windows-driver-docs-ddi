---
UID: NF:d3dkmthk.D3DKMTGetScanLine
title: D3DKMTGetScanLine function
author: windows-driver-content
description: The D3DKMTGetScanLine function determines whether the given video present source of a video present network (VidPN) is in vertical blanking mode and retrieves the current scan line.
old-location: display\d3dkmtgetscanline.htm
old-project: display
ms.assetid: 052507ec-4a26-4bb6-8876-c03a9c81f412
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DKMTGetScanLine
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMTGetScanLine
req.alt-loc: Gdi32.dll,API-MS-Win-dx-d3dkmt-l1-1-0.dll,API-MS-Win-dx-d3dkmt-l1-1-1.dll,API-MS-Win-DX-D3DKMT-L1-1-2.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Gdi32.lib
req.dll: Gdi32.dll
req.irql: 
req.typenames: D3DKMT_DRIVERVERSION
---

# D3DKMTGetScanLine function



## -description
The <b>D3DKMTGetScanLine</b> function determines whether the given video present source of a video present network (VidPN) is in vertical blanking mode and retrieves the current scan line.



## -syntax

````
NTSTATUS D3DKMTGetScanLine(
  _Inout_ D3DKMT_GETSCANLINE *pData
);
````


## -parameters

### -param pData [in, out]

A pointer to a <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_getscanline.md">D3DKMT_GETSCANLINE</a> structure that contains the vertical blanking status of a video present source.


## -returns
<b>D3DKMTGetScanLine</b> returns one of the following values:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The vertical blanking status and scan line were successfully retrieved.
<dl>
<dt><b>STATUS_DEVICE_REMOVED</b></dt>
</dl>The graphics adapter was stopped.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>Parameters were validated and determined to be incorrect.

 

This function might also return other <b>NTSTATUS</b> values.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_getscanline.md">D3DKMT_GETSCANLINE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMTGetScanLine function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

