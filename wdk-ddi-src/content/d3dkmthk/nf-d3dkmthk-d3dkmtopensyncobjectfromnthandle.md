---
UID: NF:d3dkmthk.D3DKMTOpenSyncObjectFromNtHandle
title: D3DKMTOpenSyncObjectFromNtHandle function
author: windows-driver-content
description: Maps an NT process handle to a graphics processing unit (GPU) synchronization object.
old-location: display\d3dkmtopensyncobjectfromnthandle.htm
old-project: display
ms.assetid: 202695a2-cfe3-423f-b4da-a9ad312c5168
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.d3dkmtopensyncobjectfromnthandle, D3DKMTOpenSyncObjectFromNtHandle function [Display Devices], d3dkmthk/D3DKMTOpenSyncObjectFromNtHandle, D3DKMTOpenSyncObjectFromNtHandle
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
req.lib: GDI32.lib
req.dll: GDI32.dll
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	GDI32.dll
-	API-MS-Win-dx-d3dkmt-l1-1-0.dll
-	API-MS-Win-dx-d3dkmt-l1-1-1.dll
-	API-MS-Win-DX-D3DKMT-L1-1-2.dll
apiname:
-	D3DKMTOpenSyncObjectFromNtHandle
product: Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---

# D3DKMTOpenSyncObjectFromNtHandle function


## -description


Maps an NT process handle to a graphics processing unit (GPU) synchronization object.


## -syntax


````
EXTERN_C _Check_return_ NTSTATUS APIENTRY D3DKMTOpenSyncObjectFromNtHandle(
  _Inout_ D3DKMT_OPENSYNCOBJECTFROMNTHANDLE *pObject
);
````


## -parameters





#### - pObject [in, out]

A pointer to a <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_opensyncobjectfromnthandle.md">D3DKMT_OPENSYNCOBJECTFROMNTHANDLE</a> structure that describes information that is required to perform the mapping.


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
The mapping was performed successfully.

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
</table> 

This function might also return other NTSTATUS values.



## -see-also

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_opensyncobjectfromnthandle.md">D3DKMT_OPENSYNCOBJECTFROMNTHANDLE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMTOpenSyncObjectFromNtHandle function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

