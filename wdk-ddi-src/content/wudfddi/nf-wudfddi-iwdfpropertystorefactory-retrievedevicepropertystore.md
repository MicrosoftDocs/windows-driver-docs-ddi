---
UID: NF:wudfddi.IWDFPropertyStoreFactory.RetrieveDevicePropertyStore
title: IWDFPropertyStoreFactory::RetrieveDevicePropertyStore method
author: windows-driver-content
description: The RetrieveDevicePropertyStore method retrieves a property store interface that drivers can use to access the registry.
old-location: wdf\iwdfpropertystorefactory_retrievedevicepropertystore.htm
old-project: wdf
ms.assetid: 23a4c968-b1d1-48f4-9ea9-b97c4b5b4208
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RetrieveDevicePropertyStore method, RetrieveDevicePropertyStore method, IWDFPropertyStoreFactory interface, IWDFPropertyStoreFactory, wdf.iwdfpropertystorefactory_retrievedevicepropertystore, UMDFDeviceObjectRef_79101c30-a5ab-44cf-8fa0-52394d1cce32.xml, IWDFPropertyStoreFactory interface, RetrieveDevicePropertyStore method, wudfddi/IWDFPropertyStoreFactory::RetrieveDevicePropertyStore, IWDFPropertyStoreFactory::RetrieveDevicePropertyStore, RetrieveDevicePropertyStore, umdf.iwdfpropertystorefactory_retrievedevicepropertystore
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
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
-	IWDFPropertyStoreFactory.RetrieveDevicePropertyStore
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IWDFPropertyStoreFactory::RetrieveDevicePropertyStore method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <a href="https://msdn.microsoft.com/be47a1f0-03ff-432c-a3ef-5978c9b48183">RetrieveDevicePropertyStore</a> method retrieves a property store interface that drivers can use to access the registry.


## -syntax


````
HRESULT RetrieveDevicePropertyStore(
  [in]  PWDF_PROPERTY_STORE_ROOT          RootSpecifier,
  [in]  WDF_PROPERTY_STORE_RETRIEVE_FLAGS Flags,
  [in]  REGSAM                            DesiredAccess,
  [in]  PCWSTR                            SubkeyPath,
  [out] IWDFNamedPropertyStore2           **PropertyStore,
  [out] WDF_PROPERTY_STORE_DISPOSITION    *Disposition
);
````


## -parameters




### -param RootSpecifier [in]

The address of a driver-allocated <a href="..\wudfddi_types\ns-wudfddi_types-_wdf_property_store_root.md">WDF_PROPERTY_STORE_ROOT</a> structure. The driver fills in this structure to identify the property store that <a href="https://msdn.microsoft.com/be47a1f0-03ff-432c-a3ef-5978c9b48183">RetrieveDevicePropertyStore</a> retrieves.


### -param Flags [in]

A <a href="..\wudfddi_types\ne-wudfddi_types-_wdf_property_store_retrieve_flags.md">WDF_PROPERTY_STORE_RETRIEVE_FLAGS</a>-typed flag that specifies whether UMDF should create a specified registry entry if it does not exist, and whether the new entry should be deleted when Windows restarts.


### -param DesiredAccess [in]

A REGSAM-typed bit mask that specifies the types of access to the registry that you want your driver to have. The REGSAM type is defined in Winreg.h, and is described in the Windows SDK at <a href="http://go.microsoft.com/fwlink/p/?linkid=138045">REGSAM</a>. The bit mask must not specify GENERIC_WRITE, KEY_CREATE_SUB_KEY, or WRITE_DAC access. (Although the driver cannot specify KEY_CREATE_SUB_KEY, its call to <a href="https://msdn.microsoft.com/be47a1f0-03ff-432c-a3ef-5978c9b48183">RetrieveDevicePropertyStore</a> can create a subkey.)


### -param SubkeyPath [in]

A pointer to a caller-supplied character string that represents the name of a subkey located under the registry key that the <i>RootSpecifier</i> parameter specifies. This parameter is optional and can be <b>NULL</b>. See more information in Remarks.


### -param PropertyStore [out]

The address of a location that receives a pointer to an <a href="..\wudfddi\nn-wudfddi-iwdfnamedpropertystore2.md">IWDFNamedPropertyStore2</a> interface. The driver uses this interface to access values in the registry.


### -param Disposition [out]

The address of a location that receives a <a href="..\wudfddi_types\ne-wudfddi_types-_wdf_property_store_disposition.md">WDF_PROPERTY_STORE_DISPOSITION</a>-typed value. 


## -returns



<a href="https://msdn.microsoft.com/be47a1f0-03ff-432c-a3ef-5978c9b48183">RetrieveDevicePropertyStore</a> returns S_OK if the operation succeeds. Otherwise, the method might return one of the following values:
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
The caller provided an invalid input argument.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">
An attempt to allocate memory failed.

</td>
</tr>
</table> 

This method might return one of the other values that Winerror.h contains





## -remarks


Your driver can call <a href="https://msdn.microsoft.com/be47a1f0-03ff-432c-a3ef-5978c9b48183">RetrieveDevicePropertyStore</a> to obtain access to the driver's software key, the current device's hardware key, keys for the device interfaces that the current device supports, or the <b>DEVICEMAP</b> key.

If you supply the <i>SubkeyPath</i> parameter, you must use a unique name, such as the driver's service name. A driver might use a subkey to store device-specific information.

For more information about using <a href="https://msdn.microsoft.com/be47a1f0-03ff-432c-a3ef-5978c9b48183">RetrieveDevicePropertyStore</a> to access the registry, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-the-registry-in-umdf-1-x-drivers">Using the Registry in UMDF-based Drivers</a>. 



## -see-also

<a href="..\wudfddi\nn-wudfddi-iwdfpropertystorefactory.md">IWDFPropertyStoreFactory</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff558842">IWDFDevice::RetrieveDevicePropertyStore</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556982">IWDFDeviceInitialize::RetrieveDevicePropertyStore</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFPropertyStoreFactory::RetrieveDevicePropertyStore method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

