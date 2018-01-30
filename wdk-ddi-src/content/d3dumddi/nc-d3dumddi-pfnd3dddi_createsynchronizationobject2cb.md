---
UID: NC:d3dumddi.PFND3DDDI_CREATESYNCHRONIZATIONOBJECT2CB
title: PFND3DDDI_CREATESYNCHRONIZATIONOBJECT2CB
author: windows-driver-content
description: Creates a GPU synchronization object that a device context can signal and wait for. Used by WDDM 1.2 and later user-mode display drivers.
old-location: display\pfncreatesynchronizationobject2cb.htm
old-project: display
ms.assetid: 9B0F058C-B71F-4A4F-A053-F9381A5FD3A8
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.pfncreatesynchronizationobject2cb, pfnCreateSynchronizationObject2Cb callback function [Display Devices], pfnCreateSynchronizationObject2Cb, PFND3DDDI_CREATESYNCHRONIZATIONOBJECT2CB, PFND3DDDI_CREATESYNCHRONIZATIONOBJECT2CB, d3dumddi/pfnCreateSynchronizationObject2Cb
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
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
req.lib: 
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	d3dumddi.h
apiname:
-	pfnCreateSynchronizationObject2Cb
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_CREATESYNCHRONIZATIONOBJECT2CB callback


## -description


Creates a GPU synchronization object that a device context can signal and wait for. Used by WDDM 1.2 and later user-mode display drivers.


## -prototype


````
PFND3DDDI_CREATESYNCHRONIZATIONOBJECT2CB pfnCreateSynchronizationObject2Cb;

_Check_return_ HRESULT APIENTRY CALLBACK* pfnCreateSynchronizationObject2Cb(
  _In_    HANDLE                                hDevice,
  _Inout_ D3DDDICB_CREATESYNCHRONIZATIONOBJECT2 *pData
)
{ ... }
````


## -parameters




### -param hDevice [in]

A handle to the display device (that is, the graphics context) that will own the synchronization object that <i>pfnCreateSynchronizationObject2Cb</i> creates.


### -param *






#### - pData [in, out]

A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddicb_createsynchronizationobject2.md">D3DDDICB_CREATESYNCHRONIZATIONOBJECT2</a> structure that describes the synchronization object to create.


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
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The synchronization object was successfully created.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">

        The function could not allocate memory that was required for it to complete.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
Parameters were validated and determined to be incorrect.

</td>
</tr>
</table> 

This function might also return other HRESULT values.



## -remarks


The <i>pfnCreateSynchronizationObject2Cb</i> function returns a kernel-mode handle to the newly created synchronization object in the <b>hSyncObject</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_d3dddicb_createsynchronizationobject2.md">D3DDDICB_CREATESYNCHRONIZATIONOBJECT2</a> structure that the <i>pData</i> parameter points to. The user-mode display driver passes this handle in calls to the following functions:
<ul>
<li>

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_destroysynchronizationobjectcb.md">pfnDestroySynchronizationObjectCb</a>


</li>
<li>

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_signalsynchronizationobjectcb.md">pfnSignalSynchronizationObjectCb</a>


</li>
<li>

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_signalsynchronizationobject2cb.md">pfnSignalSynchronizationObject2Cb</a>


</li>
<li>

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_waitforsynchronizationobjectcb.md">pfnWaitForSynchronizationObjectCb</a>


</li>
<li>

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_waitforsynchronizationobject2cb.md">pfnWaitForSynchronizationObject2Cb</a>


</li>
</ul>


## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddicb_createsynchronizationobject2.md">D3DDDICB_CREATESYNCHRONIZATIONOBJECT2</a>

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_signalsynchronizationobject2cb.md">pfnSignalSynchronizationObject2Cb</a>

<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicecallbacks.md">D3DDDI_DEVICECALLBACKS</a>

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_destroysynchronizationobjectcb.md">pfnDestroySynchronizationObjectCb</a>

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_waitforsynchronizationobject2cb.md">pfnWaitForSynchronizationObject2Cb</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_CREATESYNCHRONIZATIONOBJECT2CB callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

