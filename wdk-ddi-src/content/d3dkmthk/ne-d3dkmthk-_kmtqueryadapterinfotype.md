---
UID: NE:d3dkmthk._KMTQUERYADAPTERINFOTYPE
title: KMTQUERYADAPTERINFOTYPE (d3dkmthk.h)
description: Learn more about the KMTQUERYADAPTERINFOTYPE enumeration.
ms.date: 02/03/2025
req.header: d3dkmthk.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows Vista (WDDM 1.0)
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

## -description

A **KMTQUERYADAPTERINFOTYPE** value indicates the specific [**Type**](ns-d3dkmthk-_d3dkmt_queryadapterinfo.md) of adapter information being retrieved by [**D3DKMTQueryAdapterInfo**](nf-d3dkmthk-d3dkmtqueryadapterinfo.md).

## -enum-fields

### -field KMTQAITYPE_UMDRIVERPRIVATE

The buffer that **pPrivateDriverData** points to is populated with private driver data in a vendor-specific format. To read and process the private data, a tight coupling between the user-mode driver (UMD) and the kernel-mode display miniport driver (KMD) must exist.

### -field KMTQAITYPE_UMDRIVERNAME

The **pPrivateDriverData** member points to a [**D3DKMT_UMDFILENAMEINFO**](ns-d3dkmthk-_d3dkmt_umdfilenameinfo.md) structure that is filled with the name of the UMD.

### -field KMTQAITYPE_UMOPENGLINFO

**pPrivateDriverData** points to a [**D3DKMT_OPENGLINFO**](ns-d3dkmthk-_d3dkmt_openglinfo.md) structure that contains information about the OpenGL ICD. Non-DirectX applications can use this name to call the OpenGL ICD directly, although such usage is not recommended.

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

Supported starting with Windows 7.

### -field KMTQAITYPE_DRIVERVERSION

**pPrivateDriverData** points to a variable that contains a [**D3DKMT_DRIVERVERSION**](ne-d3dkmthk-_qai_driverversion.md)-typed value that indicates the version of the display driver model that the KMD supports.

Supported starting with Windows 7.

### -field KMTQAITYPE_ADAPTERTYPE

**pPrivateDriverData** points to a [**D3DKMT_ADAPTERTYPE**](ns-d3dkmthk-_d3dkmt_adaptertype.md) structure that specifies the  graphics adapter type.

Supported starting with Windows 8.

### -field KMTQAITYPE_OUTPUTDUPLCONTEXTSCOUNT

**pPrivateDriverData** points to a [**D3DKMT_OUTPUTDUPLCONTEXTSCOUNT**](ns-d3dkmthk-_d3dkmt_outputduplcontextscount.md) structure that specifies the  number of current [Desktop Duplication API](/windows/desktop/direct3ddxgi/desktop-dup-api) (DDA) clients that are attached to a given video present network (VidPN).

Supported starting with Windows 8.

### -field KMTQAITYPE_WDDM_1_2_CAPS

**pPrivateDriverData** points to a [**D3DKMT_WDDM_1_2_CAPS**](/windows-hardware/drivers/display/d3dkmt-wddm-1-2-caps) structure that specifies the  WDDM 1.2 and later capabilities of the graphics adapter and KMD.

Supported starting with Windows 8.

### -field KMTQAITYPE_UMD_DRIVER_VERSION

**pPrivateDriverData** points to a  [**D3DKMT_UMD_DRIVER_VERSION**](ns-d3dkmthk-_d3dkmt_umd_driver_version.md) structure that specifies UMD's version.

Supported starting with Windows 8.

### -field KMTQAITYPE_DIRECTFLIP_SUPPORT

**pPrivateDriverData** points to a [**D3DKMT_DIRECTFLIP_SUPPORT**](ns-d3dkmthk-_d3dkmt_directflip_support.md) structure that specifies whether the UMD supports Direct Flip operations.

Supported starting with Windows 8.

### -field KMTQAITYPE_MULTIPLANEOVERLAY_SUPPORT

**pPrivateDriverData** points to a [**D3DKMT_MULTIPLANEOVERLAY_SUPPORT**](ns-d3dkmthk-_d3dkmt_multiplaneoverlay_support.md) structure that specifies whether the UMD supports multiplane overlay operations.

Supported starting with Windows 8.1.

### -field KMTQAITYPE_DLIST_DRIVER_NAME

**pPrivateDriverData** points to a [**D3DKMT_DLIST_DRIVER_NAME**](ns-d3dkmthk-_d3dkmt_dlist_driver_name.md) structure that specifies the name of the driver that supports the display list (DList) feature.

Supported starting with Windows 8.1.

### -field KMTQAITYPE_WDDM_1_3_CAPS

**pPrivateDriverData** points to a [**D3DKMT_WDDM_1_3_CAPS**](../d3dkmdt/ns-d3dkmdt-_d3dkmt_wddm_1_3_caps.md) structure with information about supported WDDM 1.3 caps.

Supported starting with Windows 8.1.

### -field KMTQAITYPE_MULTIPLANEOVERLAY_HUD_SUPPORT

**pPrivateDriverData** points to a [**D3DKMT_MULTIPLANEOVERLAY_HUD_SUPPORT**](ns-d3dkmthk-_d3dkmt_multiplaneoverlay_hud_support.md) structure that specifies whether the UMD supports multiplane overlay heads-up display (HUD) operations.

Supported starting with Windows 8.1.

### -field KMTQAITYPE_WDDM_2_0_CAPS

**pPrivateDriverData** points to a [**D3DKMT_WDDM_2_0_CAPS**](../d3dkmdt/ns-d3dkmdt-_d3dkmt_wddm_2_0_caps.md) structure with information about supported WDDM 2.0 caps. Supported starting with Windows 10 (WDDM 2.0).

### -field KMTQAITYPE_NODEMETADATA

**pPrivateDriverData** points to a [**D3DKMT_NODEMETADATA**](../d3dkmdt/ns-d3dkmdt-d3dkmt_nodemetadata.md) structure that contains metadata about the node. Supported starting with Windows 10 (WDDM 2.0).

### -field KMTQAITYPE_CPDRIVERNAME

**pPrivateDriverData** points to a [**D3DKMT_CPDRIVERNAME**](ns-d3dkmthk-_d3dkmt_cpdrivername.md) structure that specifies the name of the driver that supports the content protection (CP) feature. Supported starting with Windows 10 (WDDM 2.0).

### -field KMTQAITYPE_XBOX

**pPrivateDriverData** points to a [**D3DKMT_XBOX**](ns-d3dkmthk-_d3dkmt_xbox.md) structure that specifies information about the Xbox. Supported starting with Windows 10 (WDDM 2.0).

### -field KMTQAITYPE_INDEPENDENTFLIP_SUPPORT

**pPrivateDriverData** points to a [**D3DKMT_INDEPENDENTFLIP_SUPPORT**](ns-d3dkmthk-_d3dkmt_independentflip_support.md) structure that specifies whether the UMD supports independent flip operations. Supported starting with Windows 10 (WDDM 2.0).

### -field KMTQAITYPE_MIRACASTCOMPANIONDRIVERNAME

**pPrivateDriverData** points to a [**D3DKMT_MIRACASTCOMPANIONDRIVERNAME**](ns-d3dkmthk-_d3dkmt_miracastcompaniondrivername.md) structure that specifies the name of the driver that supports the Miracast companion feature. Supported starting with Windows 10 (WDDM 2.0).

### -field KMTQAITYPE_PHYSICALADAPTERCOUNT

**pPrivateDriverData** points to a [**D3DKMT_PHYSICAL_ADAPTER_COUNT**](ns-d3dkmthk-_d3dkmt_physical_adapter_count.md) structure that specifies the number of physical adapters. Supported starting with Windows 10 (WDDM 2.0).

### -field KMTQAITYPE_PHYSICALADAPTERDEVICEIDS

**pPrivateDriverData** points to a [**D3DKMT_QUERY_DEVICE_IDS**](ns-d3dkmthk-_d3dkmt_query_device_ids.md) structure that specifies the device ID(s) of the physical adapters. Supported starting with Windows 10 (WDDM 2.0).

### -field KMTQAITYPE_DRIVERCAPS_EXT

**pPrivateDriverData** points to a [**D3DKMT_DRIVERCAPS_EXT**](../d3dkmdt/ns-d3dkmdt-d3dkmt_drivercaps_ext.md) structure that specifies extended driver capabilities. Supported starting with Windows 10 (WDDM 2.0).

### -field KMTQAITYPE_QUERY_MIRACAST_DRIVER_TYPE

**pPrivateDriverData** points to a [**D3DKMT_MIRACAST_DRIVER_TYPE**](ne-d3dkmthk-_d3dkmt_miracast_driver_type.md) value that specifies the type of Miracast driver. Supported starting with Windows 10 (WDDM 2.0).

### -field KMTQAITYPE_QUERY_GPUMMU_CAPS

**pPrivateDriverData** points to a [**D3DKMT_QUERY_GPUMMU_CAPS**](ns-d3dkmthk-_d3dkmt_query_gpummu_caps.md) structure that specifies GPU memory management unit (MMU) capabilities. Supported starting with Windows 10 (WDDM 2.0).

### -field KMTQAITYPE_QUERY_MULTIPLANEOVERLAY_DECODE_SUPPORT

**pPrivateDriverData** points to a [**D3DKMT_MULTIPLANEOVERLAY_DECODE_SUPPORT**](ns-d3dkmthk-_d3dkmt_multiplaneoverlay_decode_support.md) structure that specifies whether the UMD supports multiplane overlay decode operations. Supported starting with Windows 10 (WDDM 2.0).

### -field KMTQAITYPE_QUERY_HW_PROTECTION_TEARDOWN_COUNT

**pPrivateDriverData** points to a UNIT value that specifies the hardware protection teardown count. Supported starting with Windows 10 (WDDM 2.0).

### -field KMTQAITYPE_QUERY_ISBADDRIVERFORHWPROTECTIONDISABLED

**pPrivateDriverData** points to a [**D3DKMT_ISBADDRIVERFORHWPROTECTIONDISABLED**](ns-d3dkmthk-_d3dkmt_isbaddriverforhwprotectiondisabled.md) structure that specifies whether a bad driver for hardware protection is disabled. Supported starting with Windows 10 (WDDM 2.0).

### -field KMTQAITYPE_MULTIPLANEOVERLAY_SECONDARY_SUPPORT

**pPrivateDriverData** points to a [**D3DKMT_MULTIPLANEOVERLAY_SECONDARY_SUPPORT**](ns-d3dkmthk-_d3dkmt_multiplaneoverlay_secondary_support.md) structure that specifies whether the UMD provides multiplane overlay support for secondary displays. Supported starting with Windows 10 (WDDM 2.0).

### -field KMTQAITYPE_INDEPENDENTFLIP_SECONDARY_SUPPORT

**pPrivateDriverData** points to a [**D3DKMT_INDEPENDENTFLIP_SECONDARY_SUPPORT**](ns-d3dkmthk-_d3dkmt_independentflip_secondary_support.md) structure that specifies whether the UMD supports independent flip operations for secondary displays. Supported starting with Windows 10 (WDDM 2.0).

### -field KMTQAITYPE_PANELFITTER_SUPPORT

**pPrivateDriverData** points to a [**D3DKMT_PANELFITTER_SUPPORT**](ns-d3dkmthk-_d3dkmt_panelfitter_support.md) structure that specifies whether the UMD supports panel fitter operations. Supported starting with Windows 10, version 1607 (WDDM 2.1).

### -field KMTQAITYPE_PHYSICALADAPTERPNPKEY

**pPrivateDriverData** points to a [**D3DKMT_QUERY_PHYSICAL_ADAPTER_PNPKEY**](ns-d3dkmthk-_d3dkmt_query_physical_adapter_pnp_key.md) structure that specifies the physical adapter's plug-and-play (PNP) key. Supported starting with Windows 10, version 1703 (WDDM 2.2).

### -field KMTQAITYPE_GETSEGMENTGROUPSIZE

**pPrivateDriverData** points to a [**D3DKMT_SEGMENTGROUPSIZEINFO**](ns-d3dkmthk-_d3dkmt_segmentgroupsizeinfo.md) structure that specifies the information about the segment group size. Supported starting with Windows 10, version 1703 (WDDM 2.2).

### -field KMTQAITYPE_MPO3DDI_SUPPORT

**pPrivateDriverData** points to a [**D3DKMT_MPO3DDI_SUPPORT**](ns-d3dkmthk-_d3dkmt_mpo3ddi_support.md) structure that specifies whether the driver supports the [multiplane overlay version 3 interface](../d3dkmddi/nc-d3dkmddi-dxgkddi_checkmultiplaneoverlaysupport3.md) operations. Available starting with Windows 10, version 1703 (WDDM 2.2).

### -field KMTQAITYPE_HWDRM_SUPPORT

**pPrivateDriverData** points to a [**D3DKMT_HWDRM_SUPPORT**](ns-d3dkmthk-_d3dkmt_hwdrm_support.md) structure that specifies whether the driver supports hardware digital rights management (DRM) operations. Available starting with Windows 10, version 1703 (WDDM 2.2).

### -field KMTQAITYPE_MPOKERNELCAPS_SUPPORT

**pPrivateDriverData** points to a [**D3DKMT_MPOKERNELCAPS_SUPPORT**](ns-d3dkmthk-_d3dkmt_mpokernelcaps_support.md) structure that specifies  whether multiplane overlay kernel capabilities are supported. Available starting with Windows 10, version 1703 (WDDM 2.2).

### -field KMTQAITYPE_MULTIPLANEOVERLAY_STRETCH_SUPPORT

**pPrivateDriverData** points to a [**D3DKMT_MULTIPLANEOVERLAY_STRETCH_SUPPORT**](ns-d3dkmthk-_d3dkmt_multiplaneoverlay_stretch_support.md) structure that specifies whether the driver supports multiplane overlay stretch operations. Available starting with Windows 10, version 1703 (WDDM 2.2).

### -field KMTQAITYPE_GET_DEVICE_VIDPN_OWNERSHIP_INFO

**pPrivateDriverData** points to a [**D3DKMT_GET_DEVICE_VIDPN_OWNERSHIP_STATE**](ns-d3dkmthk-_d3dkmt_get_device_vidpn_ownership_info.md) structure that specifies the ownership state of the video present network (VidPN) for a given device. Available starting with Windows 10, version 1703 (WDDM 2.2).

### -field KMTQAITYPE_QUERYREGISTRY

**pPrivateDriverData** points to a [**D3DKMT_ADAPTERREGISTRYINFO**](ns-d3dkmthk-_d3dkmt_adapterregistryinfo.md) structure, where the last field is actually variable-sized by the caller.

This type queries the registry for information that is commonly cached during driver installation.
User-mode components must use this technique to support paravirtualized adapters, instead of relying on native OS methods. For more information, see [GPU virtualization](/windows-hardware/drivers/display/gpu-paravirtualization).

Support for this type started with Windows 10, version 1803 WDDM 2.4.

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

**pPrivateDriverData** points to a [**D3DKMT_HYBRID_DLIST_DLL_SUPPORT**](ns-d3dkmthk-d3dkmt_hybrid_dlist_dll_support.md) structure. Supported starting with Windows 10, version 2004 (WDDM 2.7).

### -field KMTQAITYPE_DISPLAY_CAPS

### -field KMTQAITYPE_WDDM_2_9_CAPS

**pPrivateDriverData** points to a [**D3DKMT_WDDM_2_9_CAPS**](../d3dkmdt/ns-d3dkmdt-d3dkmt_wddm_2_9_caps.md) structure with information about supported WDDM 2.9 caps. Supported starting with Windows Server 2022.

### -field KMTQAITYPE_CROSSADAPTERRESOURCE_SUPPORT

**pPrivateDriverData** points to a [**D3DKMT_CROSSADAPTERRESOURCE_SUPPORT**](ns-d3dkmthk-d3dkmt_crossadapterresource_support.md) structure. Supported starting with Windows Server 2022.

### -field KMTQAITYPE_WDDM_3_0_CAPS

**pPrivateDriverData** points to a [**D3DKMT_WDDM_3_0_CAPS**](../d3dkmdt/ns-d3dkmdt-d3dkmt_wddm_3_0_caps.md) structure with information about supported WDDM 3.0 caps. Supported starting with Windows 11, version 21H2.

### -field KMTQAITYPE_WSAUMDIMAGENAME

### -field KMTQAITYPE_VGPUINTERFACEID

### -field KMTQAITYPE_WDDM_3_1_CAPS

**pPrivateDriverData** points to a [**D3DKMT_WDDM_3_1_CAPS**](../d3dkmdt/ns-d3dkmdt-d3dkmt_wddm_3_1_caps.md) structure with information about supported WDDM 3.1 caps. Supported starting with Windows 11, version 22H2.

## -remarks

Each enum value denotes how to interpret the other fields of **D3DKMT_QUERYADAPTERINFO**, especially **D3DKMT_QUERYADAPTERINFO::pPrivateDriverData**.
**pPrivateDriverData** is commonly reinterpreted as a unique structure, corresponding to each enum value. Exceptions do exist, as detailed above.

## -see-also

[**D3DKMT_QUERYADAPTERINFO**](ns-d3dkmthk-_d3dkmt_queryadapterinfo.md)

[**D3DKMTQueryAdapterInfo**](nf-d3dkmthk-d3dkmtqueryadapterinfo.md)

[**PFND3DKMT_QUERYADAPTERINFO**](nc-d3dkmthk-pfnd3dkmt_queryadapterinfo.md)
