---
UID: NE:wudfddi_types._WDF_PROPERTY_STORE_ROOT_CLASS
title: _WDF_PROPERTY_STORE_ROOT_CLASS (wudfddi_types.h)
description: The WDF_PROPERTY_STORE_ROOT_CLASS enumeration identifies the registry keys that UMDF property stores represent.
old-location: wdf\wdf_property_store_root_class.htm
tech.root: wdf
ms.assetid: f26732a7-54b5-4573-ac4f-7b2b6c8db8b0
ms.date: 02/26/2018
keywords: ["_WDF_PROPERTY_STORE_ROOT_CLASS enumeration"]
ms.keywords: WDF_PROPERTY_STORE_ROOT_CLASS, WDF_PROPERTY_STORE_ROOT_CLASS enumeration, WdfPropertyStoreRootClassDeviceInterfaceKey, WdfPropertyStoreRootClassHardwareKey, WdfPropertyStoreRootClassLegacyHardwareKey, WdfPropertyStoreRootClassSoftwareKey, _WDF_PROPERTY_STORE_ROOT_CLASS, umdf.wdf_property_store_root_class, umdfstructs_4dbaed0a-3a72-4a4c-877e-83176cce54d6.xml, wdf.wdf_property_store_root_class, wudfddi_types/WDF_PROPERTY_STORE_ROOT_CLASS, wudfddi_types/WdfPropertyStoreRootClassDeviceInterfaceKey, wudfddi_types/WdfPropertyStoreRootClassHardwareKey, wudfddi_types/WdfPropertyStoreRootClassLegacyHardwareKey, wudfddi_types/WdfPropertyStoreRootClassSoftwareKey
f1_keywords:
 - "wudfddi_types/WDF_PROPERTY_STORE_ROOT_CLASS"
req.header: wudfddi_types.h
req.include-header: Wudfddi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.9
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Wudfddi_types.h
api_name:
- WDF_PROPERTY_STORE_ROOT_CLASS
product:
- Windows
targetos: Windows
req.typenames: WDF_PROPERTY_STORE_ROOT_CLASS
---

# _WDF_PROPERTY_STORE_ROOT_CLASS enumeration


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>WDF_PROPERTY_STORE_ROOT_CLASS</b> enumeration identifies the registry keys that UMDF property stores represent.


## -enum-fields




### -field WdfPropertyStoreRootClassHardwareKey

The property store represents a device's <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-the-registry-in-umdf-1-x-drivers">hardware key</a>.


### -field WdfPropertyStoreRootClassSoftwareKey

The property store represents a driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-the-registry-in-umdf-1-x-drivers">software key</a>.


### -field WdfPropertyStoreRootClassDeviceInterfaceKey

The property store represents the key for an instance of a <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-the-registry-in-umdf-1-x-drivers">device interface class</a>.


### -field WdfPropertyStoreRootClassLegacyHardwareKey

The property store represents the <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-the-registry-in-umdf-1-x-drivers">DEVICEMAP key</a>, which is used by only a few older drivers. 


## -remarks



The <b>WDF_PROPERTY_STORE_ROOT_CLASS</b> enumeration is used in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi_types/ns-wudfddi_types-_wdf_property_store_root">WDF_PROPERTY_STORE_ROOT</a> structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi_types/ns-wudfddi_types-_wdf_property_store_root">WDF_PROPERTY_STORE_ROOT</a>
 

 

