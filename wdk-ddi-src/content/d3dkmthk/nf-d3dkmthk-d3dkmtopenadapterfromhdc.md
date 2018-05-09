---
UID: NF:d3dkmthk.D3DKMTOpenAdapterFromHdc
title: D3DKMTOpenAdapterFromHdc function
author: windows-driver-content
description: The D3DKMTOpenAdapterFromHdc function maps a device context handle (HDC) to a graphics adapter handle and, if the adapter contains multiple monitor outputs, to one of those outputs.
old-location: display\d3dkmtopenadapterfromhdc.htm
old-project: display
ms.assetid: f54951fe-c79e-435e-9f31-9c39da26da6c
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: D3DKMTOpenAdapterFromHdc, D3DKMTOpenAdapterFromHdc function [Display Devices], OpenGL_Functions_f12cc225-0315-4dfa-ae28-52657ea0f030.xml, d3dkmthk/D3DKMTOpenAdapterFromHdc, display.d3dkmtopenadapterfromhdc
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Gdi32.dll
-	API-MS-Win-dx-d3dkmt-l1-1-0.dll
-	API-MS-Win-dx-d3dkmt-l1-1-1.dll
-	API-MS-Win-DX-D3DKMT-L1-1-2.dll
api_name:
-	D3DKMTOpenAdapterFromHdc
product:
- Windows
targetos: Windows
req.typenames: 
---

# D3DKMTOpenAdapterFromHdc function


## -description


The <b>D3DKMTOpenAdapterFromHdc</b> function maps a device context handle (HDC) to a graphics adapter handle and, if the adapter contains multiple monitor outputs, to one of those outputs.


## -parameters




### -param Arg1

TBD




#### - pData [in, out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff548121">D3DKMT_OPENADAPTERFROMHDC</a> structure that describes the parameters that are required to perform the mapping.


## -returns



<b>D3DKMTOpenAdapterFromHdc</b> returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The mapping was performed successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NO_MEMORY</b></dt>
</dl>
</td>
<td width="60%">
The kernel ran out of the resources that would enable it to open another handle.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
Parameters were validated and determined to be incorrect or the Windows Vista display driver model was not used.

</td>
</tr>
</table>
 

This function might also return other <b>NTSTATUS</b> values.




## -remarks



A graphics adapter corresponds to a video card. A monitor output corresponds to a head on a video card. A system with a single video card contains only one adapter. However, if the video card supports multiple heads, it supports outputting to multiple monitors.


#### Examples

The following code example demonstrates how an OpenGL ICD can use <b>D3DKMTOpenAdapterFromHdc</b> to retrieve the graphics adapter handle and the output for the primary monitor from the HDC.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>HRESULT GetPrimaryAdapterHandle(HANDLE* phAdapter, UINT* pOutput)
{
    D3DKMT_OPENADAPTERFROMHDC OpenAdapterData;
    DISPLAY_DEVICE dd;
    HDC hdc;
    int i;

    *phAdapter = NULL;
    *pOutput = 0;
    memset(&amp;dd, 0, sizeof (dd));
    dd.cb = sizeof dd;

    for (i = 0; EnumDisplayDevicesA(NULL, i, &amp;dd, 0); ++i) {
        if (dd.StateFlags &amp; DISPLAY_DEVICE_PRIMARY_DEVICE) {
            break;
        }
    }

    hdc = CreateDC (NULL, dd.DeviceName, NULL, NULL);
    if (hdc == NULL) {
        return E_FAIL;
    }

    OpenAdapterData.hDc = hdc;
    if (NT_SUCCESS((*pfnKTOpenAdapterFromHdc)(&amp;OpenAdapterData))) {
        DeleteDC(hdc);
        *phAdapter = OpenAdapterData.hAdapter;
        *pOutput = OpenAdapterData.VidPnSourceId;
        return S_OK;
    }
    DeleteDC(hdc);

    return E_FAIL;
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548121">D3DKMT_OPENADAPTERFROMHDC</a>
 

 

