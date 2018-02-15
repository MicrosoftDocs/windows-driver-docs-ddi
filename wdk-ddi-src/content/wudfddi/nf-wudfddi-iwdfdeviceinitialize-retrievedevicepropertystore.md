---
UID: NF:wudfddi.IWDFDeviceInitialize.RetrieveDevicePropertyStore
title: IWDFDeviceInitialize::RetrieveDevicePropertyStore method
author: windows-driver-content
description: The RetrieveDevicePropertyStore method retrieves a device property store that clients can read and write device properties through.
old-location: wdf\iwdfdeviceinitialize_retrievedevicepropertystore.htm
old-project: wdf
ms.assetid: 57d03610-b195-4691-8ee9-26c93560700c
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: UMDFDeviceObjectRef_88af313a-0b2d-472b-b96c-549a500b0782.xml, RetrieveDevicePropertyStore method, IWDFDeviceInitialize, IWDFDeviceInitialize interface, RetrieveDevicePropertyStore method, IWDFDeviceInitialize::RetrieveDevicePropertyStore, wdf.iwdfdeviceinitialize_retrievedevicepropertystore, RetrieveDevicePropertyStore, wudfddi/IWDFDeviceInitialize::RetrieveDevicePropertyStore, umdf.iwdfdeviceinitialize_retrievedevicepropertystore, RetrieveDevicePropertyStore method, IWDFDeviceInitialize interface
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
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
req.lib: wudfddi.h
req.dll: WUDFx.dll
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	WUDFx.dll
apiname:
-	IWDFDeviceInitialize.RetrieveDevicePropertyStore
product: Windows
targetos: Windows
req.typenames: "*PPOWER_ACTION, POWER_ACTION"
req.product: Windows 10 or later.
---

# IWDFDeviceInitialize::RetrieveDevicePropertyStore method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <a href="https://msdn.microsoft.com/be47a1f0-03ff-432c-a3ef-5978c9b48183">RetrieveDevicePropertyStore</a> method retrieves a device property store that clients can read and write device properties through.


## -syntax


````
HRESULT RetrieveDevicePropertyStore(
  [in, optional]  PCWSTR                            pcwszServiceName,
  [in]            WDF_PROPERTY_STORE_RETRIEVE_FLAGS Flags,
  [out]           IWDFNamedPropertyStore            **ppPropStore,
  [out, optional] WDF_PROPERTY_STORE_DISPOSITION    *pDisposition
);
````


## -parameters




### -param pcwszServiceName [in, optional]

A pointer to a <b>NULL</b>-terminated string that represents the name of the device property store. This parameter is optional. The driver can pass <b>NULL</b> if the driver does not supply a name for a device property store. 


### -param Flags [in]

A <a href="..\wudfddi_types\ne-wudfddi_types-_wdf_property_store_retrieve_flags.md">WDF_PROPERTY_STORE_RETRIEVE_FLAGS</a>-typed value that identifies how to retrieve the device property store. 


### -param ppPropStore [out]

A pointer to a buffer that receives a pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfnamedpropertystore.md">IWDFNamedPropertyStore</a> interface that is used to retrieve device properties.


### -param pDisposition [out, optional]

A pointer to a variable that receives a <a href="..\wudfddi_types\ne-wudfddi_types-_wdf_property_store_disposition.md">WDF_PROPERTY_STORE_DISPOSITION</a>-typed value that identifies whether the framework created the device property store or the device property store already existed. This parameter is optional. The driver can pass <b>NULL</b> if the driver does not require the disposition information. 


## -returns




<a href="https://msdn.microsoft.com/be47a1f0-03ff-432c-a3ef-5978c9b48183">RetrieveDevicePropertyStore</a> returns S_OK if the operation succeeds. Otherwise, this method returns one of the error codes that are defined in Winerror.h.




## -remarks



The caller should call the <b>Release</b> method of the <a href="..\wudfddi\nn-wudfddi-iwdfnamedpropertystore.md">IWDFNamedPropertyStore</a> interface after finishing with the property store. 

For more information, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-the-registry-in-umdf-1-x-drivers">Using the Registry in UMDF-based Drivers</a>.




## -see-also

<a href="..\wudfddi_types\ne-wudfddi_types-_wdf_property_store_retrieve_flags.md">WDF_PROPERTY_STORE_RETRIEVE_FLAGS</a>



<a href="..\wudfddi_types\ne-wudfddi_types-_wdf_property_store_disposition.md">WDF_PROPERTY_STORE_DISPOSITION</a>



<a href="..\wudfddi\nn-wudfddi-iwdfnamedpropertystore.md">IWDFNamedPropertyStore</a>



<a href="..\wudfddi\nn-wudfddi-iwdfdeviceinitialize.md">IWDFDeviceInitialize</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFDeviceInitialize::RetrieveDevicePropertyStore method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

