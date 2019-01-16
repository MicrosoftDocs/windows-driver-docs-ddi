---
UID: NF:wudfddi.IWDFUnifiedPropertyStoreFactory.RetrieveUnifiedDevicePropertyStore
title: IWDFUnifiedPropertyStoreFactory::RetrieveUnifiedDevicePropertyStore
description: The RetrieveUnifiedDevicePropertyStore method retrieves a unified property store interface.
old-location: wdf\iwdfunifiedpropertystorefactory_retrieveunifieddevicepropertystore.htm
tech.root: wdf
ms.assetid: A54E56A6-9A6C-435D-83FD-84BB0E072C74
ms.date: 02/26/2018
ms.keywords: IWDFUnifiedPropertyStoreFactory interface,RetrieveUnifiedDevicePropertyStore method, IWDFUnifiedPropertyStoreFactory.RetrieveUnifiedDevicePropertyStore, IWDFUnifiedPropertyStoreFactory::RetrieveUnifiedDevicePropertyStore, RetrieveUnifiedDevicePropertyStore, RetrieveUnifiedDevicePropertyStore method, RetrieveUnifiedDevicePropertyStore method,IWDFUnifiedPropertyStoreFactory interface, umdf.iwdfunifiedpropertystorefactory_retrieveunifieddevicepropertystore, wdf.iwdfunifiedpropertystorefactory_retrieveunifieddevicepropertystore, wudfddi/IWDFUnifiedPropertyStoreFactory::RetrieveUnifiedDevicePropertyStore
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
req.lib: 
req.dll: WUDFx.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WUDFx.dll
api_name:
-	IWDFUnifiedPropertyStoreFactory.RetrieveUnifiedDevicePropertyStore
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFUnifiedPropertyStoreFactory::RetrieveUnifiedDevicePropertyStore


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>RetrieveUnifiedDevicePropertyStore</b> method retrieves a unified property store interface.


## -parameters




### -param RootSpecifier [in]

The address of a driver-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff561453">WDF_PROPERTY_STORE_ROOT</a> structure. The driver fills in this structure to identify the unified property store that <b>RetrieveUnifiedDevicePropertyStore</b> retrieves.


### -param PropertyStore [out]

The address of a location that receives a pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/hh451399">IWDFUnifiedPropertyStore</a> interface.


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

The <b>RootClass</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561453">WDF_PROPERTY_STORE_ROOT</a> structure pointed to by <i>RootSpecifier</i> must be set to <b>WdfPropertyStoreRootClassHardwareKey</b> or <b>WdfPropertyStoreRootClassDeviceInterfaceKey</b>.

In addition, if <b>RootClass</b> is set to <b>WdfPropertyStoreRootClassHardwareKey</b>, then the <b>Qualifier.HardwareKey.ServiceName</b> member of <i>RootSpecifier</i> must be NULL.

For more information about accessing the registry, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-the-registry-in-umdf-1-x-drivers">Using the Registry in UMDF-based Drivers</a>.


#### Examples

The following code example retrieves a unified property store interface.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>HRESULT
GetDevicePropertyStore(
    _In_  IWDFDevice *                  FxDevice,
    _Out_ IWDFUnifiedPropertyStore **   ppUnifiedPropertyStore
    )
{
    HRESULT hr;
    IWDFUnifiedPropertyStore *          pUnifiedPropertyStore = NULL;
    WDF_PROPERTY_STORE_ROOT             RootSpecifier;
    IWDFUnifiedPropertyStoreFactory *   pUnifiedPropertyStoreFactory = NULL;

    HRESULT hrQI = FxDevice-&gt;QueryInterface(
                        IID_PPV_ARGS(&amp;pUnifiedPropertyStoreFactory)
                        );
    WUDF_TEST_DRIVER_ASSERT(SUCCEEDED(hrQI));

    RootSpecifier.LengthCb = sizeof(RootSpecifier);
    RootSpecifier.RootClass = WdfPropertyStoreRootClassHardwareKey;
    RootSpecifier.Qualifier.HardwareKey.ServiceName = NULL;
    
    hr = pUnifiedPropertyStoreFactory-&gt;RetrieveUnifiedDevicePropertyStore(
            &amp;RootSpecifier,
            &amp;pUnifiedPropertyStore
            );

    if (FAILED(hr))
    {
        TraceEvents(
            TRACE_LEVEL_ERROR, 
            TEST_TRACE_DEVICE, 
            "Failed to retrieve unified property store for device: ”
            “hr = %!HRESULT!",
            hr
            );
        goto exit;
    }

    *ppUnifiedPropertyStore = pUnifiedPropertyStore;

exit:
    SAFE_RELEASE(pUnifiedPropertyStoreFactory);
    
    return hr;
}
</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh451399">IWDFUnifiedPropertyStore</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451403">IWDFUnifiedPropertyStoreFactory</a>
 

 

