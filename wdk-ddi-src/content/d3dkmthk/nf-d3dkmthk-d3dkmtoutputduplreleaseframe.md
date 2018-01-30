---
UID: NF:d3dkmthk.D3DKMTOutputDuplReleaseFrame
title: D3DKMTOutputDuplReleaseFrame function
author: windows-driver-content
description: Indicates that the driver has finished processing the duplicated desktop image.
old-location: display\d3dkmtoutputduplreleaseframe.htm
old-project: display
ms.assetid: 07bbc201-0320-4f26-be0a-27c06763813f
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DKMTOutputDuplReleaseFrame, PFND3DKMT_OUTPUTDUPLRELEASEFRAME, d3dkmthk/D3DKMTOutputDuplReleaseFrame, display.d3dkmtoutputduplreleaseframe, D3DKMTOutputDuplReleaseFrame function [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	D3DKMTOutputDuplReleaseFrame
product: Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---

# D3DKMTOutputDuplReleaseFrame function


## -description


Indicates that the driver has finished processing the duplicated desktop image.


## -syntax


````
EXTERN_C _Check_return_ NTSTATUS APIENTRY D3DKMTOutputDuplReleaseFrame(
  _Inout_ D3DKMT_OUTPUTDUPL_RELEASE_FRAME *pData
);
````


## -parameters





#### - pData [in, out]

A pointer to a <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_outputdupl_release_frame.md">D3DKMT_OUTPUTDUPL_RELEASE_FRAME</a> structure that defines the duplicated desktop image that is to be released.


## -returns


Returns one of the following values:
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
The function performed successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER </b></dt>
</dl>
</td>
<td width="60%">

         Parameters were validated and determined to be incorrect.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
The context of the process could not be found.

</td>
</tr>
</table> 

This function might also return other NTSTATUS values.



## -see-also

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_outputdupl_release_frame.md">D3DKMT_OUTPUTDUPL_RELEASE_FRAME</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMTOutputDuplReleaseFrame function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

