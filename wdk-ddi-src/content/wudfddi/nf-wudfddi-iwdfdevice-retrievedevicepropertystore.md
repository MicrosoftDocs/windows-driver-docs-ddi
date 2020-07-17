---
UID: NF:wudfddi.IWDFDevice.RetrieveDevicePropertyStore
title: IWDFDevice::RetrieveDevicePropertyStore (wudfddi.h)
description: The RetrieveDevicePropertyStore method retrieves a property store interface that drivers can use to access the registry.
old-location: wdf\iwdfdevice_retrievedevicepropertystore.htm
tech.root: wdf
ms.assetid: be47a1f0-03ff-432c-a3ef-5978c9b48183
ms.date: 02/26/2018
keywords: ["IWDFDevice::RetrieveDevicePropertyStore"]
ms.keywords: IWDFDevice interface,RetrieveDevicePropertyStore method, IWDFDevice.RetrieveDevicePropertyStore, IWDFDevice::RetrieveDevicePropertyStore, RetrieveDevicePropertyStore, RetrieveDevicePropertyStore method, RetrieveDevicePropertyStore method,IWDFDevice interface, UMDFDeviceObjectRef_daa1a135-2ca7-4d59-92b0-b44c917af73d.xml, umdf.iwdfdevice_retrievedevicepropertystore, wdf.iwdfdevice_retrievedevicepropertystore, wudfddi/IWDFDevice::RetrieveDevicePropertyStore
f1_keywords:
 - "wudfddi/IWDFDevice.RetrieveDevicePropertyStore"
 - "IWDFDevice.RetrieveDevicePropertyStore"
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.5
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: WUDFx.dll
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- WUDFx.dll
api_name:
- IWDFDevice.RetrieveDevicePropertyStore
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFDevice::RetrieveDevicePropertyStore


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>RetrieveDevicePropertyStore</b> method retrieves a property store interface that drivers can use to access the registry.


## -parameters




### -param pcwszServiceName [in, optional]

A pointer to a <b>NULL</b>-terminated string that represents the name of the device property store. This parameter is optional. The driver can pass <b>NULL</b> if the driver does not supply a name for a device property store. 


### -param Flags [in]

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi_types/ne-wudfddi_types-_wdf_property_store_retrieve_flags">WDF_PROPERTY_STORE_RETRIEVE_FLAGS</a>-typed value that identifies how to retrieve the device property store. 


### -param ppPropStore [out]

A pointer to a buffer that receives a pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfnamedpropertystore">IWDFNamedPropertyStore</a> interface. The driver uses this interface to access values in the registry.


### -param pDisposition [out, optional]

A pointer to a variable that receives a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi_types/ne-wudfddi_types-_wdf_property_store_disposition">WDF_PROPERTY_STORE_DISPOSITION</a>-typed value that identifies whether the framework created the device property store or the device property store already existed. This parameter is optional. The driver can pass <b>NULL</b> if the driver does not require the disposition information. 


## -returns



<b>RetrieveDevicePropertyStore</b> returns S_OK if the operation succeeds. Otherwise, this method returns one of the error codes that are defined in Winerror.h.




## -remarks



The caller should call the <b>Release</b> method of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfnamedpropertystore">IWDFNamedPropertyStore</a> interface after finishing with the property store. 

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-the-registry-in-umdf-1-x-drivers">Using the Registry in UMDF-based Drivers</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfdevice">IWDFDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdeviceinitialize-retrievedevicepropertystore">IWDFDeviceInitialize::RetrieveDevicePropertyStore</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfnamedpropertystore">IWDFNamedPropertyStore</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfpropertystorefactory-retrievedevicepropertystore">IWDFPropertyStoreFactory::RetrieveDevicePropertyStore</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi_types/ne-wudfddi_types-_wdf_property_store_disposition">WDF_PROPERTY_STORE_DISPOSITION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi_types/ne-wudfddi_types-_wdf_property_store_retrieve_flags">WDF_PROPERTY_STORE_RETRIEVE_FLAGS</a>
 

 

