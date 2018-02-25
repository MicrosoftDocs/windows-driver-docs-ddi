---
UID: NF:d3dkmthk.D3DKMTDestroyPagingQueue
title: D3DKMTDestroyPagingQueue function
author: windows-driver-content
description: D3DKMTDestroyPagingQueue waits for a paging queue to finish all operations queued to it, and destroys it along with the associated sync object.
old-location: display\d3dkmtdestroypagingqueue.htm
old-project: display
ms.assetid: 470563BD-F185-4CA2-B4AD-06E1AABD36AD
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , 3, D, D3DKMTDestroyPagingQueue, D3DKMTDestroyPagingQueue function [Display Devices], K, M, P, Q, T, a, d3dkmthk/D3DKMTDestroyPagingQueue, display.d3dkmtdestroypagingqueue, e, g, i, n, o, r, s, t, u, y"
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
-	GDI32.dll
-	API-MS-Win-DX-D3DKMT-L1-1-2.dll
apiname:
-	D3DKMTDestroyPagingQueue
product: Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---

# D3DKMTDestroyPagingQueue function


## -description


<b>D3DKMTDestroyPagingQueue</b> waits for a paging queue to finish all operations queued to it, and destroys it along with the associated sync object.


## -syntax


````
EXTERN_C _Check_return_ NTSTATUS APIENTRY D3DKMTDestroyPagingQueue(
  _Inout_ D3DDDI_DESTROYPAGINGQUEUE *pData
);
````


## -parameters






#### - pData [in, out]

A pointer to a <a href="..\d3dukmdt\ns-d3dukmdt-d3dddi_destroypagingqueue.md">D3DDDI_DESTROYPAGINGQUEUE</a> structure that describes the operation.


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
</table>
 

This function might also return other <b>NTSTATUS</b> values.




## -remarks



In addition to <b>hPagingQueue</b>, this device driver interface (DDI) invalidates <b>hSyncObject</b> and <b>FenceValueCPUVirtualAddress</b> values returned from <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtcreatepagingqueue.md">D3DKMTCreatePagingQueue</a>.




## -see-also

<a href="..\d3dukmdt\ns-d3dukmdt-d3dddi_destroypagingqueue.md">D3DDDI_DESTROYPAGINGQUEUE</a>



<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtcreatepagingqueue.md">D3DKMTCreatePagingQueue</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMTDestroyPagingQueue function%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

