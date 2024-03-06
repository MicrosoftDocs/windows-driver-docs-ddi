---
UID: NE:d3dkmthk._KMTQUERYADAPTERINFOTYPE
title: _KMTQUERYADAPTERINFOTYPE (d3dkmthk.h)
description: Each KMTQUERYADAPTERINFOTYPE value correlates to a specific piece of adapter information being retrieved by D3DKMQueryAdapterInfo.
ms.date: 02/23/2022
keywords: ["KMTQUERYADAPTERINFOTYPE enumeration"]
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
targetos: Windows
tech.root: display
f1_keywords:
 - _KMTQUERYADAPTERINFOTYPE
 - d3dkmthk/_KMTQUERYADAPTERINFOTYPE
 - KMTQUERYADAPTERINFOTYPE
 - d3dkmthk/KMTQUERYADAPTERINFOTYPE
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - _KMTQUERYADAPTERINFOTYPE
 - KMTQUERYADAPTERINFOTYPE
---

# KMTQUERYADAPTERINFOTYPE enumeration

## -description

Each **KMTQUERYADAPTERINFOTYPE** value correlates to a specific piece of adapter information being retrieved by [**D3DKMQueryAdapterInfo**](nf-d3dkmthk-d3dkmtqueryadapterinfo.md).

## -enum-fields

### -field KMTQAITYPE_UMDRIVERPRIVATE

The buffer that **pPrivateDriverData** points to is populated with private driver data in a vendor-specific format. To read and process the private data, a tight coupling between user mode driver and the display miniport driver must exist.

### -field KMTQAITYPE_UMDRIVERNAME

The **pPrivateDriverData** member points to a [**D3DKMT_UMDFILENAMEINFO**](ns-d3dkmthk-_d3dkmt_umdfilenameinfo.md) structure that is filled with the name of the OpenGL ICD that depends on the particular version of DirectX. Non-DirectX applications can use this name to call the OpenGL ICD directly, although such usage is not recommended.

### -field KMTQAITYPE_UMOPENGLINFO

**pPrivateDriverData** points to a [**D3DKMT_OPENGLINFO**](ns-d3dkmthk-_d3dkmt_openglinfo.md) structure that contains information about the OpenGL ICD.

### -field KMTQAITYPE_GETSEGMENTSIZE

**pPrivateDriverData** points to a [**D3DKMT_SEGMENTSIZEINFO**](ns-d3dkmthk-_d3dkmt_segmentsizeinfo.md) structure that contains information about the size of memory and aperture segments.

### -field KMTQAITYPE_ADAPTERGUID

**pPrivateDriverData** points to a variable that contains the GUID for the adapter.

### -field KMTQAITYPE_FLIPQUEUEINFO

**pPrivateDriverData** points to a [**D3DKMT_FLIPQUEUEINFO**](ns-d3dkmthk-_d3dkmt_flipqueueinfo.md) structure that contains information about the queue of flip operations.

### -field KMTQAITYPE_ADAPTERADDRESS

**pPrivateDriverData** points to a [**D3DKMT_ADAPTERADDRESS**](ns-d3dkmthk-_d3dkmt_adapteraddress.md) structure that contains information about the physical location on the PCI bus of the adapter.

### -field KMTQAITYPE_SETWORKINGSETINFO

**pPrivateDriverData** points to a [**D3DKMT_WORKINGSETINFO**](ns-d3dkmthk-_d3dkmt_workingsetinfo.md) structure that contains information about the working set.

### -field KMTQAITYPE_ADAPTERREGISTRYINFO

**pPrivateDriverData** points to a [**D3DKMT_ADAPTERREGISTRYINFO**](ns-d3dkmthk-_d3dkmt_adapterregistryinfo.md) structure that contains registry information about the graphics adapter.

### -field KMTQAITYPE_CURRENTDISPLAYMODE

**pPrivateDriverData** points to a [**D3DKMT_CURRENTDISPLAYMODE**](ns-d3dkmthk-_d3dkmt_currentdisplaymode.md) structure that contains the current display mode.

### -field KMTQAITYPE_MODELIST

**pPrivateDriverData** points to an array of [**D3DKMT_DISPLAYMODE**](ns-d3dkmthk-_d3dkmt_displaymode.md) structures for the list of display modes.

### -field KMTQAITYPE_CHECKDRIVERUPDATESTATUS

**pPrivateDriverData** points to the driver update status.

### -field KMTQAITYPE_VIRTUALADDRESSINFO

**pPrivateDriverData** points to a [D3DKMT_VIRTUALADDRESSINFO](ns-d3dkmthk-_d3dkmt_virtualaddressinfo.md) structure.

Returns information about virtual addressing support.

Supported starting with  Windows 7.

### -field KMTQAITYPE_DRIVERVERSION

**pPrivateDriverData** points to a variable that contains a [**D3DKMT_DRIVERVERSION**](ne-d3dkmthk-_qai_driverversion.md)-typed value that indicates the version of the display driver model that the display miniport driver supports.

Supported starting with  Windows 7.

### -field KMTQAITYPE_ADAPTERTYPE

**pPrivateDriverData** points to a [**D3DKMT_ADAPTERTYPE**](ns-d3dkmthk-_d3dkmt_adaptertype.md) structure that specifies the  graphics adapter type.

Supported starting with  Windows 8.

### -field KMTQAITYPE_OUTPUTDUPLCONTEXTSCOUNT

**pPrivateDriverData** points to a [**D3DKMT_OUTPUTDUPLCONTEXTSCOUNT**](ns-d3dkmthk-_d3dkmt_outputduplcontextscount.md) structure that specifies the  number of current [Desktop Duplication API](/windows/desktop/direct3ddxgi/desktop-dup-api) (DDA) clients that are attached to a given video present network (VidPN).

Supported starting with  Windows 8.

### -field KMTQAITYPE_WDDM_1_2_CAPS

**pPrivateDriverData** points to a [**D3DKMT_WDDM_1_2_CAPS**](/windows-hardware/drivers/display/d3dkmt-wddm-1-2-caps) structure that specifies the  WDDM 1.2 and later capabilities of the graphics adapter and display miniport driver.

Supported starting with  Windows 8.

### -field KMTQAITYPE_UMD_DRIVER_VERSION

**pPrivateDriverData** points to a  [**D3DKMT_UMD_DRIVER_VERSION**](ns-d3dkmthk-_d3dkmt_umd_driver_version.md) structure that specifies the  user-mode driver version.

Supported starting with  Windows 8.

### -field KMTQAITYPE_DIRECTFLIP_SUPPORT

**pPrivateDriverData** points to a [**D3DKMT_DIRECTFLIP_SUPPORT**](ns-d3dkmthk-_d3dkmt_directflip_support.md) structure that specifies whether the user-mode driver supports Direct Flip operations.

Supported starting with  Windows 8.

### -field KMTQAITYPE_MULTIPLANEOVERLAY_SUPPORT

Reserved for future use.

Supported starting with  Windows 8.1.

### -field KMTQAITYPE_DLIST_DRIVER_NAME

Supported starting with  Windows 8.1.

### -field KMTQAITYPE_WDDM_1_3_CAPS

**pPrivateDriverData** points to a [**D3DKMT_WDDM_1_3_CAPS**](../d3dkmdt/ns-d3dkmdt-_d3dkmt_wddm_1_3_caps.md) structure with information about supported WDDM 1.3 caps.

Supported starting with  Windows 8.1.

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

Support for this type started with Windows 10 version 1803.

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

### -field KMTQAITYPE_DRIVER_DESCRIPTION

### -field KMTQAITYPE_DRIVER_DESCRIPTION_RENDER

### -field KMTQAITYPE_SCANOUT_CAPS

### -field KMTQAITYPE_DISPLAY_UMDRIVERNAME

### -field KMTQAITYPE_PARAVIRTUALIZATION_RENDER

### -field KMTQAITYPE_SERVICENAME

### -field KMTQAITYPE_WDDM_2_7_CAPS

### -field KMTQAITYPE_TRACKEDWORKLOAD_SUPPORT

### -field KMTQAITYPE_HYBRID_DLIST_DLL_SUPPORT

**pPrivateDriverData** points to a [**D3DKMT_HYBRID_DLIST_DLL_SUPPORT**](ns-d3dkmthk-d3dkmt_hybrid_dlist_dll_support.md) structure. Supported starting with Windows 10, version 2004.

### -field KMTQAITYPE_DISPLAY_CAPS

### -field KMTQAITYPE_WDDM_2_9_CAPS

**pPrivateDriverData** points to a [**D3DKMT_WDDM_2_9_CAPS**](../d3dkmdt/ns-d3dkmdt-d3dkmt_wddm_2_9_caps.md) structure with information about supported WDDM 2.9 caps. Supported starting with Windows Server 2022.

### -field KMTQAITYPE_CROSSADAPTERRESOURCE_SUPPORT

**pPrivateDriverData** points to a [**D3DKMT_CROSSADAPTERRESOURCE_SUPPORT**](ns-d3dkmthk-d3dkmt_crossadapterresource_support.md) structure. Supported starting with Windows Server 2022.

### -field KMTQAITYPE_WDDM_3_0_CAPS

**pPrivateDriverData** points to a [**D3DKMT_WDDM_3_0_CAPS**](../d3dkmdt/ns-d3dkmdt-d3dkmt_wddm_3_0_caps.md) structure with information about supported WDDM 3.0 caps. Supported starting with Windows 11, version 21H2.

## -remarks

Each enum value denotes how to interpret the other fields of **D3DKMT_QUERYADAPTERINFO**, especially **D3DKMT_QUERYADAPTERINFO::pPrivateDriverData**.
**pPrivateDriverData** is commonly reinterpreted as a unique structure, corresponding to each enum value. Exceptions do exist, as detailed above.

## -see-also

[**KMTQUERYADAPTERINFOTYPE**](ne-d3dkmthk-_kmtqueryadapterinfotype.md)

[**D3DKMT_QUERYADAPTERINFO**](ns-d3dkmthk-_d3dkmt_queryadapterinfo.md)

[**D3DKMTQueryAdapterInfo**](nf-d3dkmthk-d3dkmtqueryadapterinfo.md)

[**PFND3DKMT_QUERYADAPTERINFO**](nc-d3dkmthk-pfnd3dkmt_queryadapterinfo.md)
