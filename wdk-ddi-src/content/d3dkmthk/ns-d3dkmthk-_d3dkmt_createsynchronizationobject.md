---
UID: NS:d3dkmthk._D3DKMT_CREATESYNCHRONIZATIONOBJECT
title: "_D3DKMT_CREATESYNCHRONIZATIONOBJECT"
author: windows-driver-content
description: The D3DKMT_CREATESYNCHRONIZATIONOBJECT structure describes a synchronization object that the D3DKMTCreateSynchronizationObject function creates.
old-location: display\d3dkmt_createsynchronizationobject.htm
old-project: display
ms.assetid: 2e4e1fd7-9a36-4c35-8d9d-932a0d2e60a2
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DKMT_CREATESYNCHRONIZATIONOBJECT, D3DKMT_CREATESYNCHRONIZATIONOBJECT structure [Display Devices], OpenGL_Structs_918a7c9b-3dba-4af3-aa2c-334861301304.xml, _D3DKMT_CREATESYNCHRONIZATIONOBJECT, d3dkmthk/D3DKMT_CREATESYNCHRONIZATIONOBJECT, display.d3dkmt_createsynchronizationobject
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmthk.h
api_name:
-	D3DKMT_CREATESYNCHRONIZATIONOBJECT
product: Windows
targetos: Windows
req.typenames: D3DKMT_CREATESYNCHRONIZATIONOBJECT
---

# _D3DKMT_CREATESYNCHRONIZATIONOBJECT structure


## -description


The D3DKMT_CREATESYNCHRONIZATIONOBJECT structure describes a synchronization object that the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546869">D3DKMTCreateSynchronizationObject</a> function creates.


## -struct-fields




### -field hDevice

[in] A handle to the device that the synchronization object is associated with.


### -field Info

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff544657">D3DDDI_SYNCHRONIZATIONOBJECTINFO</a> structure that describes information about the kernel-mode synchronization object.


### -field hSyncObject

[out] A D3DKMT_HANDLE data type that represents a kernel-mode handle to the kernel-mode synchronization object. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544657">D3DDDI_SYNCHRONIZATIONOBJECTINFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546869">D3DKMTCreateSynchronizationObject</a>
 

 

