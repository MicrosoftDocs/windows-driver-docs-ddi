---
UID: NE:wudfddi_types._WDF_PROPERTY_STORE_RETRIEVE_FLAGS
title: _WDF_PROPERTY_STORE_RETRIEVE_FLAGS (wudfddi_types.h)
description: The WDF_PROPERTY_STORE_RETRIEVE_FLAGS enumeration contains values that indicate whether UMDF should create a registry key if the key does not already exist.
old-location: wdf\wdf_property_store_retrieve_flags.htm
tech.root: wdf
ms.assetid: bd64ef0d-b2e7-4f82-87a8-77fe98677fd9
ms.date: 02/26/2018
keywords: ["WDF_PROPERTY_STORE_RETRIEVE_FLAGS enumeration"]
ms.keywords: WDF_PROPERTY_STORE_RETRIEVE_FLAGS, WDF_PROPERTY_STORE_RETRIEVE_FLAGS enumeration, WdfPropertyStoreCreateIfMissing, WdfPropertyStoreCreateVolatile, WdfPropertyStoreNormal, WdfPropertyStoreRetrieveFlagsMask, _WDF_PROPERTY_STORE_RETRIEVE_FLAGS, umdf.wdf_property_store_retrieve_flags, umdfstructs_c11a65c3-e37f-4adb-b480-1682d8e51700.xml, wdf.wdf_property_store_retrieve_flags, wudfddi_types/WDF_PROPERTY_STORE_RETRIEVE_FLAGS, wudfddi_types/WdfPropertyStoreCreateIfMissing, wudfddi_types/WdfPropertyStoreCreateVolatile, wudfddi_types/WdfPropertyStoreNormal, wudfddi_types/WdfPropertyStoreRetrieveFlagsMask
f1_keywords:
 - "wudfddi_types/WDF_PROPERTY_STORE_RETRIEVE_FLAGS"
 - "WDF_PROPERTY_STORE_RETRIEVE_FLAGS"
req.header: wudfddi_types.h
req.include-header: Wudfddi.h
req.target-type: Windows
req.target-min-winverclnt: 
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Wudfddi_types.h
api_name:
- WDF_PROPERTY_STORE_RETRIEVE_FLAGS
targetos: Windows
req.typenames: WDF_PROPERTY_STORE_RETRIEVE_FLAGS
---

# _WDF_PROPERTY_STORE_RETRIEVE_FLAGS enumeration


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>WDF_PROPERTY_STORE_RETRIEVE_FLAGS</b> enumeration contains values that indicate whether  UMDF should create a registry key if the key does not already exist.


## -enum-fields




### -field WdfPropertyStoreNormal

Do not create the registry key if it does not exist.


### -field WdfPropertyStoreCreateIfMissing

Create the registry key if it does not exist. The key will be <i>nonvolatile</i>, which means that it will not be deleted when Windows restarts.


### -field WdfPropertyStoreCreateVolatile

Create the registry key if it does not exist. The key will be volatile, which means that it will be deleted when Windows restarts. This flag is available in UMDF versions 1.9 and later. 


### -field WdfPropertyStoreRetrieveFlagsMask

Reserved for system use. 


## -remarks



<b>WDF_PROPERTY_STORE_RETRIEVE_FLAGS</b> enumeration values are used as input to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice-retrievedevicepropertystore">IWDFDevice::RetrieveDevicePropertyStore</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdeviceinitialize-retrievedevicepropertystore">IWDFDeviceInitialize::RetrieveDevicePropertyStore</a>, and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfpropertystorefactory-retrievedevicepropertystore">IWDFPropertyStoreFactory::RetrieveDevicePropertyStore</a> methods.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice-retrievedevicepropertystore">IWDFDevice::RetrieveDevicePropertyStore</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdeviceinitialize-retrievedevicepropertystore">IWDFDeviceInitialize::RetrieveDevicePropertyStore</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfpropertystorefactory-retrievedevicepropertystore">IWDFPropertyStoreFactory::RetrieveDevicePropertyStore</a>
 

 

