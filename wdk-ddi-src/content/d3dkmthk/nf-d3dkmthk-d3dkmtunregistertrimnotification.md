---
UID: NF:d3dkmthk.D3DKMTUnregisterTrimNotification
title: D3DKMTUnregisterTrimNotification function
author: windows-driver-content
description: D3DKMTUnregisterTrimNotification is used to remove a callback registration for a kernel mode device receiving notifications from a graphics framework (such as OpenGL).
old-location: display\d3dkmtunregistertrimnotification.htm
old-project: display
ms.assetid: C90A5200-F6AF-4B7B-BB66-D76D4C3AA8EE
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DKMTUnregisterTrimNotification, display.d3dkmtunregistertrimnotification, D3DKMTUnregisterTrimNotification function [Display Devices], d3dkmthk/D3DKMTUnregisterTrimNotification
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
-	API-MS-Win-DX-D3DKMT-L1-1-1.dll
-	API-MS-Win-DX-D3DKMT-L1-1-2.dll
apiname:
-	D3DKMTUnregisterTrimNotification
product: Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---

# D3DKMTUnregisterTrimNotification function


## -description


<b>D3DKMTUnregisterTrimNotification</b> is used to remove a callback registration for a kernel mode device receiving notifications from a graphics framework (such as OpenGL).
<div class="alert"><b>Note</b>  The callback must be unregistered prior to unloading the module that contains the callback function and destroying the registered kernel mode device.</div><div> </div>

## -syntax


````
EXTERN_C _Check_return_ NTSTATUS APIENTRY D3DKMTUnregisterTrimNotification(
  _Inout_ D3DKMT_UNREGISTERTRIMNOTIFICATION *pData
);
````


## -parameters






#### - pData [in, out]

A pointer to a <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_unregistertrimnotification.md">D3DKMT_UNREGISTERTRIMNOTIFICATION</a> structure that describes the operation.


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
The operation was performed successfully.

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
 

This function might also return other <b>NTSTATUS</b> values.




## -see-also

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_unregistertrimnotification.md">D3DKMT_UNREGISTERTRIMNOTIFICATION</a>



<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtregistertrimnotification.md">D3DKMTRegisterTrimNotification</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMTUnregisterTrimNotification function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

