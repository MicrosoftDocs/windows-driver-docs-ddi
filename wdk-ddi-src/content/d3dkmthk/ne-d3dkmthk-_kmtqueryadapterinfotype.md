---
UID: NE:d3dkmthk._KMTQUERYADAPTERINFOTYPE
title: _KMTQUERYADAPTERINFOTYPE
author: windows-driver-content
description: The available types of display adapters in the registry.
ms.assetid: bb3888be-1948-4b72-b3f4-c04ff33f2573
ms.date: 10/19/2018
ms.topic: enum
ms.keywords: _KMTQUERYADAPTERINFOTYPE, KMTQUERYADAPTERINFOTYPE,
req.header: d3dkmthk.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.typenames: KMTQUERYADAPTERINFOTYPE
topic_type:
-	apiref
api_type:
-	HeaderDef
api_location:
-	d3dkmthk.h
api_name:
-	_KMTQUERYADAPTERINFOTYPE
product: 
- Windows
targetos: Windows
tech.root: display
---

# _KMTQUERYADAPTERINFOTYPE enumeration

## -description
Each **KMTQUERYADAPTERINFOTYPE** value correlates to a specific piece of adapter information being retrieved by QueryAdapterInfo.
Each enum value denotes how to interpret the other fields of **D3DKMT_QUERYADAPTERINFO**, especially **D3DKMT_QUERYADAPTERINFO::pPrivateDriverData**.
**pPrivateDriverData** is commonly reinterpreted as a unique structure, corresponding to each enum value.
Exceptions do exist, as detailed below.

## -enum-fields

### -field KMTQAITYPE_UMDRIVERPRIVATE
The buffer that <b>pPrivateDriverData</b> points to is populated with private driver data in a vendor-specific format. To read and process the private data, a tight coupling between user mode driver and the display miniport driver must exist.

### -field KMTQAITYPE_UMDRIVERNAME
The <b>pPrivateDriverData</b> member points to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff548384">D3DKMT_UMDFILENAMEINFO</a> structure that is filled with the name of the OpenGL ICD that depends on the particular version of DirectX. Non-DirectX applications can use this name to call the OpenGL ICD directly, although such usage is not recommended.

### -field KMTQAITYPE_UMOPENGLINFO
<b>pPrivateDriverData</b> points to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff548123">D3DKMT_OPENGLINFO</a> structure that contains information about the OpenGL ICD.

### -field KMTQAITYPE_GETSEGMENTSIZE
<b>pPrivateDriverData</b> points to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff548256">D3DKMT_SEGMENTSIZEINFO</a> structure that contains information about the size of memory and aperture segments.

### -field KMTQAITYPE_ADAPTERGUID
<b>pPrivateDriverData</b> points to a variable that contains the GUID for the adapter.

### -field KMTQAITYPE_FLIPQUEUEINFO
<b>pPrivateDriverData</b> points to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff548010">D3DKMT_FLIPQUEUEINFO</a> structure that contains information about the queue of flip operations.

### -field KMTQAITYPE_ADAPTERADDRESS
<b>pPrivateDriverData</b> points to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff547280">D3DKMT_ADAPTERADDRESS</a> structure that contains information about the physical location on the PCI bus of the adapter.

### -field KMTQAITYPE_SETWORKINGSETINFO
<b>pPrivateDriverData</b> points to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff548457">D3DKMT_WORKINGSETINFO</a> structure that contains information about the working set.

### -field KMTQAITYPE_ADAPTERREGISTRYINFO
<b>pPrivateDriverData</b> points to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff547286">D3DKMT_ADAPTERREGISTRYINFO</a> structure that contains registry information about the graphics adapter.

### -field KMTQAITYPE_CURRENTDISPLAYMODE
<b>pPrivateDriverData</b> points to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff547860">D3DKMT_CURRENTDISPLAYMODE</a> structure that contains the current display mode.

### -field KMTQAITYPE_MODELIST
<b>pPrivateDriverData</b> points to an array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff547942">D3DKMT_DISPLAYMODE</a> structures for the list of display modes.

### -field KMTQAITYPE_CHECKDRIVERUPDATESTATUS
<b>pPrivateDriverData</b> points to the driver update status.

### -field KMTQAITYPE_VIRTUALADDRESSINFO
**pPrivateDriverData** points to a [D3DKMT_VIRTUALADDRESSINFO](ns-d3dkmthk-_d3dkmt_virtualaddressinfo.md) structure.

Returns information about virtual addressing support.

Supported starting with  Windows 7.

### -field KMTQAITYPE_DRIVERVERSION
<b>pPrivateDriverData</b> points to a variable that contains a <a href="https://msdn.microsoft.com/library/windows/hardware/ff547964">D3DKMT_DRIVERVERSION</a>-typed value that indicates the version of the display driver model that the display miniport driver supports.

Supported starting with  Windows 7.

### -field KMTQAITYPE_ADAPTERTYPE
<b>pPrivateDriverData</b> points to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh439472">D3DKMT_ADAPTERTYPE</a> structure that specifies the  graphics adapter type.

Supported starting with  Windows 8.

### -field KMTQAITYPE_OUTPUTDUPLCONTEXTSCOUNT
<b>pPrivateDriverData</b> points to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh406505">D3DKMT_OUTPUTDUPLCONTEXTSCOUNT</a> structure that specifies the  number of current <a href="https://msdn.microsoft.com/523FBFAD-5D78-4EE3-A3B7-8FD5BA39DC46">Desktop Duplication API</a> (DDA) clients that are attached to a given video present network (VidPN).

Supported starting with  Windows 8.

### -field KMTQAITYPE_WDDM_1_2_CAPS
<b>pPrivateDriverData</b> points to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh406678">D3DKMT_WDDM_1_2_CAPS</a> structure that specifies the  WDDM 1.2 and later capabilities of the graphics adapter and display miniport driver.

Supported starting with  Windows 8.

### -field KMTQAITYPE_UMD_DRIVER_VERSION
<b>pPrivateDriverData</b> points to a  <a href="https://msdn.microsoft.com/library/windows/hardware/hh406598">D3DKMT_UMD_DRIVER_VERSION</a> structure that specifies the  user-mode driver version.

Supported starting with  Windows 8.

### -field KMTQAITYPE_DIRECTFLIP_SUPPORT
<b>pPrivateDriverData</b> points to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh406459">D3DKMT_DIRECTFLIP_SUPPORT</a> structure that specifies whether the user-mode driver supports Direct Flip operations.

Supported starting with  Windows 8.

### -field KMTQAITYPE_MULTIPLANEOVERLAY_SUPPORT
Reserved for future use.

Supported starting with  Windows 8.1.

### -field KMTQAITYPE_DLIST_DRIVER_NAME
Supported starting with  Windows 8.1.

### -field KMTQAITYPE_WDDM_1_3_CAPS
**pPrivateDriverData** points to a [D3DKMT_WDDM_1_3_CAPS](../d3dkmdt/ns-d3dkmdt-_d3dkmt_wddm_1_3_caps.md) structure.

Returns information about supported WDDM 1.3 caps.

Supported starting with  Windows 8.1.

### -field KMTQAITYPE_MULTIPLANEOVERLAY_HUD_SUPPORT
### -field KMTQAITYPE_WDDM_2_0_CAPS
### -field KMTQAITYPE_NODEMETADATA
### -field KMTQAITYPE_CPDRIVERNAME
### -field KMTQAITYPE_XBOX
### -field KMTQAITYPE_INDEPENDENTFLIP_SUPPORT
### -field KMTQAITYPE_MIRACASTCOMPANIONDRIVERNAME
### -field KMTQAITYPE_PHYSICALADAPTERCOUNT
### -field KMTQAITYPE_PHYSICALADAPTERDEVICEIDS
### -field KMTQAITYPE_DRIVERCAPS_EXT
### -field KMTQAITYPE_QUERY_MIRACAST_DRIVER_TYPE
### -field KMTQAITYPE_QUERY_GPUMMU_CAPS
### -field KMTQAITYPE_QUERY_MULTIPLANEOVERLAY_DECODE_SUPPORT
### -field KMTQAITYPE_QUERY_HW_PROTECTION_TEARDOWN_COUNT
### -field KMTQAITYPE_QUERY_ISBADDRIVERFORHWPROTECTIONDISABLED
### -field KMTQAITYPE_MULTIPLANEOVERLAY_SECONDARY_SUPPORT
### -field KMTQAITYPE_INDEPENDENTFLIP_SECONDARY_SUPPORT
### -field KMTQAITYPE_PANELFITTER_SUPPORT
### -field KMTQAITYPE_PHYSICALADAPTERPNPKEY
### -field KMTQAITYPE_GETSEGMENTGROUPSIZE
### -field KMTQAITYPE_MPO3DDI_SUPPORT
### -field KMTQAITYPE_HWDRM_SUPPORT
### -field KMTQAITYPE_MPOKERNELCAPS_SUPPORT
### -field KMTQAITYPE_MULTIPLANEOVERLAY_STRETCH_SUPPORT
### -field KMTQAITYPE_GET_DEVICE_VIDPN_OWNERSHIP_INFO
### -field KMTQAITYPE_QUERYREGISTRY
**pPrivateDriverData** points to a [**D3DDDI_QUERYREGISTRY_INFO**](../d3dukmdt/ns-d3dukmdt-_d3dddi_queryregistry_info.md) structure, where the last field is actually variable-sized by the caller.

This type queries the registry for information that is commonly cached during driver installation.
User mode components must use this technique to support paravirtualized adapters, instead of relying on native OS methods.

Support for this type started with Windows 10 April 2018 Update (aka. version 1803).

### -field KMTQAITYPE_KMD_DRIVER_VERSION
### -field KMTQAITYPE_BLOCKLIST_KERNEL
### -field KMTQAITYPE_BLOCKLIST_RUNTIME
### -field KMTQAITYPE_ADAPTERGUID_RENDER
### -field KMTQAITYPE_ADAPTERADDRESS_RENDER
### -field KMTQAITYPE_ADAPTERREGISTRYINFO_RENDER
### -field KMTQAITYPE_CHECKDRIVERUPDATESTATUS_RENDER
### -field KMTQAITYPE_DRIVERVERSION_RENDER
### -field KMTQAITYPE_ADAPTERTYPE_RENDER
### -field KMTQAITYPE_WDDM_1_2_CAPS_RENDER
### -field KMTQAITYPE_WDDM_1_3_CAPS_RENDER
### -field KMTQAITYPE_QUERY_ADAPTER_UNIQUE_GUID
### -field KMTQAITYPE_NODEPERFDATA
### -field KMTQAITYPE_ADAPTERPERFDATA
### -field KMTQAITYPE_ADAPTERPERFDATA_CAPS
### -field KMTQUITYPE_GPUVERSION

## -remarks

## -see-also
- [KMTQUERYADAPTERINFOTYPE](ne-d3dkmthk-_kmtqueryadapterinfotype.md)
- [D3DKMT_QUERYADAPTERINFO](ns-d3dkmthk-_d3dkmt_queryadapterinfo.md)
- [D3DKMTQueryAdapterInfo](nf-d3dkmthk-d3dkmtqueryadapterinfo.md)
- [PFND3DKMT_QUERYADAPTERINFO](nc-d3dkmthk-pfnd3dkmt_queryadapterinfo.md)