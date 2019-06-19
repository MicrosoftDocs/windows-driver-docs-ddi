---
UID: NF:wudfddi.IWDFPropertyStoreFactory.RetrieveDevicePropertyStore
title: IWDFPropertyStoreFactory::RetrieveDevicePropertyStore (wudfddi.h)
description: The RetrieveDevicePropertyStore method retrieves a property store interface that drivers can use to access the registry.
old-location: wdf\iwdfpropertystorefactory_retrievedevicepropertystore.htm
tech.root: wdf
ms.assetid: 23a4c968-b1d1-48f4-9ea9-b97c4b5b4208
ms.date: 02/26/2018
ms.keywords: IWDFPropertyStoreFactory interface,RetrieveDevicePropertyStore method, IWDFPropertyStoreFactory.RetrieveDevicePropertyStore, IWDFPropertyStoreFactory::RetrieveDevicePropertyStore, RetrieveDevicePropertyStore, RetrieveDevicePropertyStore method, RetrieveDevicePropertyStore method,IWDFPropertyStoreFactory interface, UMDFDeviceObjectRef_79101c30-a5ab-44cf-8fa0-52394d1cce32.xml, umdf.iwdfpropertystorefactory_retrievedevicepropertystore, wdf.iwdfpropertystorefactory_retrievedevicepropertystore, wudfddi/IWDFPropertyStoreFactory::RetrieveDevicePropertyStore
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
- IWDFPropertyStoreFactory.RetrieveDevicePropertyStore
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFPropertyStoreFactory::RetrieveDevicePropertyStore


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <a href="https://msdn.microsoft.com/be47a1f0-03ff-432c-a3ef-5978c9b48183">RetrieveDevicePropertyStore</a> method retrieves a property store interface that drivers can use to access the registry.


## -parameters




### -param RootSpecifier [in]

The address of a driver-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff561453">WDF_PROPERTY_STORE_ROOT</a> structure. The driver fills in this structure to identify the property store that <a href="https://msdn.microsoft.com/be47a1f0-03ff-432c-a3ef-5978c9b48183">RetrieveDevicePropertyStore</a> retrieves.


### -param Flags [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff561449">WDF_PROPERTY_STORE_RETRIEVE_FLAGS</a>-typed flag that specifies whether UMDF should create a specified registry entry if it does not exist, and whether the new entry should be deleted when Windows restarts.


### -param DesiredAccess [in]

A REGSAM-typed bit mask that specifies the types of access to the registry that you want your driver to have. The REGSAM type is defined in Winreg.h, and is described in the Windows SDK at <a href="https://go.microsoft.com/fwlink/p/?linkid=138045">REGSAM</a>. The bit mask must not specify GENERIC_WRITE, KEY_CREATE_SUB_KEY, or WRITE_DAC access. (Although the driver cannot specify KEY_CREATE_SUB_KEY, its call to <a href="https://msdn.microsoft.com/be47a1f0-03ff-432c-a3ef-5978c9b48183">RetrieveDevicePropertyStore</a> can create a subkey.)


### -param SubkeyPath [in]

A pointer to a caller-supplied character string that represents the name of a subkey located under the registry key that the <i>RootSpecifier</i> parameter specifies. This parameter is optional and can be <b>NULL</b>. See more information in Remarks.


### -param PropertyStore [out]

The address of a location that receives a pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff560168">IWDFNamedPropertyStore2</a> interface. The driver uses this interface to access values in the registry.


### -param Disposition [out]

The address of a location that receives a <a href="https://msdn.microsoft.com/library/windows/hardware/ff561440">WDF_PROPERTY_STORE_DISPOSITION</a>-typed value. 


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

For more information about using <a href="https://msdn.microsoft.com/be47a1f0-03ff-432c-a3ef-5978c9b48183">RetrieveDevicePropertyStore</a> to access the registry, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-the-registry-in-umdf-1-x-drivers">Using the Registry in UMDF-based Drivers</a>. 


#### Examples

The following code example retrieves the value that is assigned to the <b>PortName</b> entry under a device's hardware key.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>IWDFPropertyStoreFactory *pPropertyStoreFactory = NULL;
WDF_PROPERTY_STORE_ROOT RootSpecifier;
IWDFNamedPropertyStore2 * pHardwarePropertyStore2 = NULL;
PROPVARIANT comPortPV;
WCHAR portName[] = L"PortName";
HRESULT hr;
...
//
// Get the property store factory interface.
//
hr = m_FxDevice->QueryInterface(IID_PPV_ARGS(&pPropertyStoreFactory));
if (FAILED(hr))
{
    goto Exit;
}
//
//Initialize the WDF_PROPERTY_STORE_ROOT structure. We want to open the 
// \Device Parameters subkey under the device's hardware key.
//
RtlZeroMemory(&RootSpecifier,
              sizeof(WDF_PROPERTY_STORE_ROOT));
RootSpecifier.LengthCb = sizeof(WDF_PROPERTY_STORE_ROOT);
RootSpecifier.RootClass = WdfPropertyStoreRootClassHardwareKey;
RootSpecifier.Qualifier.HardwareKey.ServiceName = WDF_PROPERTY_STORE_HARDWARE_KEY_ROOT;

//
// Get the property store interface for the hardware key of the
// device that m_FxDevice represents.
//
hr = pPropertyStoreFactory->RetrieveDevicePropertyStore(
                                           &RootSpecifier,
                                           WdfPropertyStoreNormal,
                                           KEY_QUERY_VALUE,
                                           NULL,
                                           &pHardwarePropertyStore2,
                                           NULL
                                           );
if (FAILED(hr))
{
    goto Exit;
}

//
// Get the value of the "PortName" entry, which is stored under 
// the device's \Device Parameters subkey.
//
PropVariantInit(&comPortPV);
hr = pHardwarePropertyStore2->GetNamedValue(portName,
                                            &comPortPV);
if (FAILED(hr))
{
   goto Exit;
}
...
Exit:
    SAFE_RELEASE(pHardwarePropertyStore2);
    SAFE_RELEASE(pPropertyStoreFactory);
...</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff558842">IWDFDevice::RetrieveDevicePropertyStore</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556982">IWDFDeviceInitialize::RetrieveDevicePropertyStore</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560223">IWDFPropertyStoreFactory</a>
 

 

