---
UID: NC:d3dumddi.PFND3DDDI_CREATESYNCHRONIZATIONOBJECTCB
title: PFND3DDDI_CREATESYNCHRONIZATIONOBJECTCB
author: windows-driver-content
description: The pfnCreateSynchronizationObjectCb function creates a synchronization object that a device context can signal and wait for.
old-location: display\pfncreatesynchronizationobjectcb.htm
old-project: display
ms.assetid: 1b87d3cc-685a-4768-b4fd-dbe0a0cbec37
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DXGK_PTE, DXGK_PTE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: pfnCreateSynchronizationObjectCb
req.alt-loc: d3dumddi.h
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
req.typenames: DXGK_PTE
---

# PFND3DDDI_CREATESYNCHRONIZATIONOBJECTCB callback



## -description
The <b>pfnCreateSynchronizationObjectCb</b> function creates a synchronization object that a device context can signal and wait for.



## -prototype

````
PFND3DDDI_CREATESYNCHRONIZATIONOBJECTCB pfnCreateSynchronizationObjectCb;

__checkResult HRESULT APIENTRY CALLBACK pfnCreateSynchronizationObjectCb(
  _In_    HANDLE                               hDevice,
  _Inout_ D3DDDICB_CREATESYNCHRONIZATIONOBJECT *pData
)
{ ... }
````


## -parameters

### -param hDevice [in]

A handle to the display device (that is, the graphics context) that will own the synchronization object that <b>pfnCreateSynchronizationObjectCb</b> creates.


### -param pData [in, out]

A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddicb_createsynchronizationobject.md">D3DDDICB_CREATESYNCHRONIZATIONOBJECT</a> structure that describes the synchronization object to create.


## -returns
<b>pfnCreateSynchronizationObjectCb</b> returns one of the following values:
<dl>
<dt><b>S_OK</b></dt>
</dl>The synchronization object was successfully created.
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl><b>pfnCreateSynchronizationObjectCb</b> could not allocate memory that was required for it to complete.
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>Parameters were validated and determined to be incorrect.

 

This function might also return other HRESULT values.


## -remarks
The <b>pfnCreateSynchronizationObjectCb</b> function returns a kernel-mode handle to the newly created synchronization object in the <b>hSyncObject</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_d3dddicb_createsynchronizationobject.md">D3DDDICB_CREATESYNCHRONIZATIONOBJECT</a> structure that the <i>pData</i> parameter points to. The user-mode display driver passes this handle in calls to the following functions:


<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_destroysynchronizationobjectcb.md">pfnDestroySynchronizationObjectCb</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_signalsynchronizationobjectcb.md">pfnSignalSynchronizationObjectCb</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_waitforsynchronizationobjectcb.md">pfnWaitForSynchronizationObjectCb</a>



## -see-also
<dl>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_d3dddicb_createsynchronizationobject.md">D3DDDICB_CREATESYNCHRONIZATIONOBJECT</a>
</dt>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicecallbacks.md">D3DDDI_DEVICECALLBACKS</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_destroysynchronizationobjectcb.md">pfnDestroySynchronizationObjectCb</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_signalsynchronizationobjectcb.md">pfnSignalSynchronizationObjectCb</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_waitforsynchronizationobjectcb.md">pfnWaitForSynchronizationObjectCb</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_CREATESYNCHRONIZATIONOBJECTCB callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

