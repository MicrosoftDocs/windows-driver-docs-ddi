---
UID: NS:d3dkmthk._D3DKMT_CREATESYNCHRONIZATIONOBJECT2
title: _D3DKMT_CREATESYNCHRONIZATIONOBJECT2
author: windows-driver-content
description: The D3DKMT_CREATESYNCHRONIZATIONOBJECT2 structure describes a synchronization object that the D3DKMTCreateSynchronizationObject2 function creates.
old-location: display\d3dkmt_createsynchronizationobject2.htm
old-project: display
ms.assetid: fa5cf57e-826b-43f6-881d-caf2aecb2dde
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _D3DKMT_CREATESYNCHRONIZATIONOBJECT2, D3DKMT_CREATESYNCHRONIZATIONOBJECT2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: D3DKMT_CREATESYNCHRONIZATIONOBJECT2 is supported beginning with the Windows 7 operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMT_CREATESYNCHRONIZATIONOBJECT2
req.alt-loc: d3dkmthk.h
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
req.typenames: D3DKMT_CREATESYNCHRONIZATIONOBJECT2
---

# _D3DKMT_CREATESYNCHRONIZATIONOBJECT2 structure



## -description
The D3DKMT_CREATESYNCHRONIZATIONOBJECT2 structure describes a synchronization object that the <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtcreatesynchronizationobject2.md">D3DKMTCreateSynchronizationObject2</a> function creates. 



## -syntax

````
typedef struct _D3DKMT_CREATESYNCHRONIZATIONOBJECT2 {
  D3DKMT_HANDLE                     hDevice;
  D3DDDI_SYNCHRONIZATIONOBJECTINFO2 Info;
  D3DKMT_HANDLE                     hSyncObject;
} D3DKMT_CREATESYNCHRONIZATIONOBJECT2;
````


## -struct-fields

### -field hDevice

[in] A handle to the device that the synchronization object is associated with. 


### -field Info

[in] A <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_synchronizationobjectinfo2.md">D3DDDI_SYNCHRONIZATIONOBJECTINFO2</a> structure that describes information about the kernel-mode synchronization object. 


### -field hSyncObject

[out] A D3DKMT_HANDLE data type that represents a kernel-mode handle to the kernel-mode synchronization object. 


## -remarks


## -see-also
<dl>
<dt>
<a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_synchronizationobjectinfo2.md">D3DDDI_SYNCHRONIZATIONOBJECTINFO2</a>
</dt>
<dt>
<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtcreatesynchronizationobject2.md">D3DKMTCreateSynchronizationObject2</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_CREATESYNCHRONIZATIONOBJECT2 structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

