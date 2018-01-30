---
UID: NF:wudfddi.IWDFUnifiedPropertyStoreFactory.RetrieveUnifiedDevicePropertyStore
title: IWDFUnifiedPropertyStoreFactory::RetrieveUnifiedDevicePropertyStore method
author: windows-driver-content
description: The RetrieveUnifiedDevicePropertyStore method retrieves a unified property store interface.
old-location: wdf\iwdfunifiedpropertystorefactory_retrieveunifieddevicepropertystore.htm
old-project: wdf
ms.assetid: A54E56A6-9A6C-435D-83FD-84BB0E072C74
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wudfddi/IWDFUnifiedPropertyStoreFactory::RetrieveUnifiedDevicePropertyStore, IWDFUnifiedPropertyStoreFactory, RetrieveUnifiedDevicePropertyStore method, IWDFUnifiedPropertyStoreFactory::RetrieveUnifiedDevicePropertyStore, umdf.iwdfunifiedpropertystorefactory_retrieveunifieddevicepropertystore, wdf.iwdfunifiedpropertystorefactory_retrieveunifieddevicepropertystore, RetrieveUnifiedDevicePropertyStore, RetrieveUnifiedDevicePropertyStore method, IWDFUnifiedPropertyStoreFactory interface, IWDFUnifiedPropertyStoreFactory interface, RetrieveUnifiedDevicePropertyStore method
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.11
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
-	IWDFUnifiedPropertyStoreFactory.RetrieveUnifiedDevicePropertyStore
product: Windows
targetos: Windows
req.typenames: "*PPOWER_ACTION, POWER_ACTION"
req.product: Windows 10 or later.
---

# IWDFUnifiedPropertyStoreFactory::RetrieveUnifiedDevicePropertyStore method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>RetrieveUnifiedDevicePropertyStore</b> method retrieves a unified property store interface.


## -syntax


````
HRESULT RetrieveUnifiedDevicePropertyStore(
  [in]  PWDF_PROPERTY_STORE_ROOT RootSpecifier,
  [out] IWDFUnifiedPropertyStore **PropertyStore
);
````


## -parameters




### -param RootSpecifier [in]

The address of a driver-allocated <a href="..\wudfddi_types\ns-wudfddi_types-_wdf_property_store_root.md">WDF_PROPERTY_STORE_ROOT</a> structure. The driver fills in this structure to identify the unified property store that <b>RetrieveUnifiedDevicePropertyStore</b> retrieves.


### -param PropertyStore [out]

The address of a location that receives a pointer to an <a href="..\wudfddi\nn-wudfddi-iwdfunifiedpropertystore.md">IWDFUnifiedPropertyStore</a> interface.


## -returns


<b>RetrieveUnifiedDevicePropertyStore</b> returns S_OK if the operation succeeds. Otherwise, the method might return one of the following values.
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

This method might return one of the other values that <i>Winerror.h</i> contains.



## -remarks


Your driver can call <b>RetrieveUnifiedDevicePropertyStore</b> to obtain access to a current device's hardware key or a device interface key that the device supports.

The <b>RootClass</b> member of the <a href="..\wudfddi_types\ns-wudfddi_types-_wdf_property_store_root.md">WDF_PROPERTY_STORE_ROOT</a> structure pointed to by <i>RootSpecifier</i> must be set to <b>WdfPropertyStoreRootClassHardwareKey</b> or <b>WdfPropertyStoreRootClassDeviceInterfaceKey</b>.

In addition, if <b>RootClass</b> is set to <b>WdfPropertyStoreRootClassHardwareKey</b>, then the <b>Qualifier.HardwareKey.ServiceName</b> member of <i>RootSpecifier</i> must be NULL.

For more information about accessing the registry, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-the-registry-in-umdf-1-x-drivers">Using the Registry in UMDF-based Drivers</a>.



## -see-also

<a href="..\wudfddi\nn-wudfddi-iwdfunifiedpropertystorefactory.md">IWDFUnifiedPropertyStoreFactory</a>

<a href="..\wudfddi\nn-wudfddi-iwdfunifiedpropertystore.md">IWDFUnifiedPropertyStore</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFUnifiedPropertyStoreFactory::RetrieveUnifiedDevicePropertyStore method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

