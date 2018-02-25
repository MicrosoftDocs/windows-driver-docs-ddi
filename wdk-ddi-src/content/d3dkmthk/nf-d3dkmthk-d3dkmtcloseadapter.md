---
UID: NF:d3dkmthk.D3DKMTCloseAdapter
title: D3DKMTCloseAdapter function
author: windows-driver-content
description: The D3DKMTCloseAdapter function closes a graphics adapter that was previously opened by using the D3DKMTOpenAdapterFromHdc function.
old-location: display\d3dkmtcloseadapter.htm
old-project: display
ms.assetid: d8f1a47b-4ba0-41e0-a6e3-0589e1efcf06
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , 3, A, C, D, D3DKMTCloseAdapter, D3DKMTCloseAdapter function [Display Devices], K, M, OpenGL_Functions_531edcbd-0ec0-4ae7-8a1a-31ed47084bba.xml, PFND3DKMT_CLOSEADAPTER, T, a, d, d3dkmthk/D3DKMTCloseAdapter, display.d3dkmtcloseadapter, e, l, o, p, r, s, t"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Gdi32.dll
-	API-MS-Win-dx-d3dkmt-l1-1-0.dll
-	API-MS-Win-dx-d3dkmt-l1-1-1.dll
-	API-MS-Win-DX-D3DKMT-L1-1-2.dll
apiname:
-	D3DKMTCloseAdapter
product: Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---

# D3DKMTCloseAdapter function


## -description


The <b>D3DKMTCloseAdapter</b> function closes a graphics adapter that was previously opened by using the <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtopenadapterfromhdc.md">D3DKMTOpenAdapterFromHdc</a> function.


## -syntax


````
NTSTATUS APIENTRY D3DKMTCloseAdapter(
  _In_ const D3DKMT_CLOSEADAPTER *pData
);
````


## -parameters




### -param D3DKMT_CLOSEADAPTER

TBD




#### - pData [in]

A pointer to a <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_closeadapter.md">D3DKMT_CLOSEADAPTER</a> structure that specifies the adapter to close.


## -returns



<b>D3DKMTCloseAdapter</b> returns one of the following values:

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
The adapter was closed successfully.

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
 

This function might also return other NTSTATUS values.




## -see-also

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_closeadapter.md">D3DKMT_CLOSEADAPTER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMTCloseAdapter function%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

