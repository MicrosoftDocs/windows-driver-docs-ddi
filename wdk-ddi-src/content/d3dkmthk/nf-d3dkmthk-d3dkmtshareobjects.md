---
UID: NF:d3dkmthk.D3DKMTShareObjects
title: D3DKMTShareObjects function (d3dkmthk.h)
description: Shares resource objects that were created with the D3DKMTCreateAllocation, D3DKMTCreateKeyedMutex2, and D3DKMTCreateSynchronizationObject2 functions.
old-location: display\d3dkmtshareobjects.htm
ms.assetid: 853c4e73-b571-4b68-8690-bbef7a726c8e
ms.date: 05/10/2018
keywords: ["D3DKMTShareObjects function"]
ms.keywords: D3DKMTShareObjects, D3DKMTShareObjects function [Display Devices], d3dkmthk/D3DKMTShareObjects, display.d3dkmtshareobjects
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
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - D3DKMTShareObjects
 - d3dkmthk/D3DKMTShareObjects
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - GDI32.dll
 - API-MS-Win-dx-d3dkmt-l1-1-0.dll
 - API-MS-Win-dx-d3dkmt-l1-1-1.dll
 - API-MS-Win-DX-D3DKMT-L1-1-2.dll
api_name:
 - D3DKMTShareObjects
---

# D3DKMTShareObjects function


## -description

Shares resource objects that were created with  the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtcreateallocation">D3DKMTCreateAllocation</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtcreatekeyedmutex2">D3DKMTCreateKeyedMutex2</a>, and  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtcreatesynchronizationobject2">D3DKMTCreateSynchronizationObject2</a> functions.

## -parameters

### -param cObjects 

[in]
The number of resource objects specified by the <i>hObjects</i> parameter.

The number of resource objects must be ≤<b>D3DKMT_MAX_OBJECTS_PER_HANDLE</b>.

### -param hObjects 

[in]
A pointer to an array of local kernel-mode handles that specify the resource objects to be shared.

For more information on using <i>hObjects</i>, see the Remarks section.

### -param pObjectAttributes 

[in]
A pointer to an <a href="https://docs.microsoft.com/windows/win32/api/ntdef/ns-ntdef-_object_attributes">OBJECT_ATTRIBUTES</a> structure that specifies attributes of the  resource objects.

### -param dwDesiredAccess 

[in]
Specifies read and write access for the resource.

### -param phSharedNtHandle 

[out]
A pointer to a shared NT handle  that specifies the resource objects.

This parameter must be <b>NULL</b> if the <b>NtSecuritySharing</b> flag value is not set. For more information, see the Remarks section.

## -remarks

Objects to be shared using  <b>D3DKMTShareObjects</b>  must first be created with the <b>NtSecuritySharing</b> flag value set. This flag value is available in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_createallocationflags">D3DKMT_CREATEALLOCATIONFLAGS</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_createkeyedmutex2_flags">D3DKMT_CREATEKEYEDMUTEX2_FLAGS</a>, and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddi_synchronizationobject_flags">D3DDDI_SYNCHRONIZATIONOBJECT_FLAGS</a> structures.

This function must specify handles through the <i>hObjects</i> parameter only to the following  combinations of input object array types:

<ul>
<li>an allocation</li>
<li>an allocation, a keyed mutex, and a synchronization object</li>
<li>a synchronization object</li>
</ul>
The operating system will reject any other input handle combinations.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddi_synchronizationobject_flags">D3DDDI_SYNCHRONIZATIONOBJECT_FLAGS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtcreateallocation">D3DKMTCreateAllocation</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtcreatekeyedmutex2">D3DKMTCreateKeyedMutex2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtcreatesynchronizationobject2">D3DKMTCreateSynchronizationObject2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_createallocationflags">D3DKMT_CREATEALLOCATIONFLAGS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_createkeyedmutex2_flags">D3DKMT_CREATEKEYEDMUTEX2_FLAGS</a>

