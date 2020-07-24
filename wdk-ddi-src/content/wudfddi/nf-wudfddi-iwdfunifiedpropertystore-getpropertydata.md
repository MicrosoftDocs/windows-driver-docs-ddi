---
UID: NF:wudfddi.IWDFUnifiedPropertyStore.GetPropertyData
title: IWDFUnifiedPropertyStore::GetPropertyData (wudfddi.h)
description: The GetPropertyData method retrieves the current setting for a device property.
old-location: wdf\iwdfunifiedpropertystore_getpropertydata.htm
tech.root: wdf
ms.assetid: 0AAEB2F1-0449-4F0E-807A-1D2420CF6858
ms.date: 02/26/2018
keywords: ["IWDFUnifiedPropertyStore::GetPropertyData"]
ms.keywords: GetPropertyData, GetPropertyData method, GetPropertyData method,IWDFUnifiedPropertyStore interface, IWDFUnifiedPropertyStore interface,GetPropertyData method, IWDFUnifiedPropertyStore.GetPropertyData, IWDFUnifiedPropertyStore::GetPropertyData, umdf.iwdfunifiedpropertystore_getpropertydata, wdf.iwdfunifiedpropertystore_getpropertydata, wudfddi/IWDFUnifiedPropertyStore::GetPropertyData
f1_keywords:
 - "wudfddi/IWDFUnifiedPropertyStore.GetPropertyData"
 - "IWDFUnifiedPropertyStore.GetPropertyData"
req.header: wudfddi.h
req.include-header: 
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- WUDFx.dll
api_name:
- IWDFUnifiedPropertyStore.GetPropertyData
targetos: Windows
req.typenames: 
---

# IWDFUnifiedPropertyStore::GetPropertyData


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetPropertyData</b> method retrieves the current setting for a device property.



## -parameters




### -param PropertyKey [in]

A pointer to a <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/dn315031(v=vs.85)">DEVPROPKEY</a> structure that specifies the device property key.


### -param Lcid [in]

Specifies a locale identifier. Set this parameter either to a language-specific LCID value or to LOCALE_NEUTRAL. The LOCALE_NEUTRAL LCID specifies that the property is language-neutral (that is, not specific to any language). Do not set this parameter to LOCALE_SYSTEM_DEFAULT or LOCALE_USER_DEFAULT. For more information about language-specific LCID values, see <a href="https://docs.microsoft.com/openspecs/windows_protocols/ms-lcid/63d3d639-7fd2-4afb-abbe-0d5b5551eef8">LCID Structure</a>.


### -param Flags [in]

Reserved for system use. Drivers should set this value to 0.


### -param PropertyDataSize [in]

The size, in bytes, of the buffer that <i>PropertyData</i> points to.


### -param PropertyData [out, optional]

A pointer to the device property data.


### -param PropertyDataRequiredSize [out]

A pointer to a ULONG to receive the size of the property information that is returned in <i>PropertyData</i>.


### -param PropertyType [out]

A pointer to a <a href="https://docs.microsoft.com/previous-versions/ff543546(v=vs.85)">DEVPROPTYPE</a> value. If <b>GetPropertyData</b> completes successfully, the method uses <i>PropertyType</i> to supply the type of data that is returned in the <i>PropertyData</i> buffer. 


## -returns



<b>GetPropertyData</b> returns S_OK if the operation succeeds. Otherwise, the method might return the following values.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">
The framework's attempt to allocate memory failed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HRESULT_FROM_NT(STATUS_BUFFER_TOO_SMALL)</b></dt>
</dl>
</td>
<td width="60%">
 The <i>PropertyDataRequiredSize</i> parameter contains the size of the required buffer.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HRESULT_FROM_WIN32 (ERROR_INVALID_PARAMETER)</b></dt>
</dl>
</td>
<td width="60%">
If the driver specifies <b>WdfPropertyStoreRootClassDeviceInterfaceKey</b>, the requested interface must be one that the UMDF driver previously registered.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HRESULT_FROM_WIN32 (STATUS_NOT_SUPPORTED)</b></dt>
</dl>
</td>
<td width="60%">
The driver can request device interface property data only  starting with  Windows 8.

</td>
</tr>
</table>
 

This method might return one of the other values that <i>Winerror.h</i> contains.




## -remarks



Framework-based drivers use the <b>GetPropertyData</b> method to retrieve device properties that are defined as part of the unified device property model.

In particular, you can use this method to retrieve a device's <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-the-registry-in-umdf-1-x-drivers">hardware key</a> or an instance of a device interface class. When you call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfunifiedpropertystorefactory-retrieveunifieddevicepropertystore">IWDFUnifiedPropertyStoreFactory::RetrieveUnifiedDevicePropertyStore</a>, set the <i>RootSpecifier</i> parameter's <b>RootClass</b> member to <b>WdfPropertyStoreRootClassHardwareKey</b> or <b>WdfPropertyStoreRootClassDeviceInterfaceKey</b>.

If you specify  <b>WdfPropertyStoreRootClassHardwareKey</b>, then when you call <b>GetPropertyData</b>, you must provide a custom <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/dn315031(v=vs.85)">DEVPROPKEY</a> value in the <i>PropertyKey</i> parameter, and  not a PnP-defined key. The value must have been previously set by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfunifiedpropertystore-setpropertydata">SetPropertyData</a>, a <a href="https://docs.microsoft.com/windows-hardware/drivers/install/using-device-installation-functions">SetupDI device property function</a>, or by using the <a href="https://docs.microsoft.com/windows-hardware/drivers/install/inf-addproperty-directive">INF AddProperty directive</a>.

For more information about device properties, see <a href="https://docs.microsoft.com/windows-hardware/drivers/image/device-properties">Device Properties</a>.

For more information about accessing the registry, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-the-registry-in-umdf-1-x-drivers">Using the Registry in UMDF-based Drivers</a>.


#### Examples

For variable size properties, the driver should make two passes to retrieve the property data. First, the driver should pass a NULL buffer in the <i>PropertyData</i> parameter, and set <i>PropertyDataSize</i> to 0.
Then, the driver should then allocate a buffer based on the <i>PropertyDataRequiredSize</i> returned and call <b>GetPropertyData</b> again, passing the allocated buffer.

The following example demonstrates this 
pattern.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>HRESULT
GetFriendlyName(
    _In_ IWDFUnifiedPropertyStore * pUnifiedPropertyStore
    )
{
    HRESULT hr = S_OK;
    DEVPROPTYPE type;
    ULONG requiredSize;
    BYTE * friendlyNameBuffer = NULL;
    ULONG friendlyNameBufferSize;

    hr = pUnifiedPropertyStore->GetPropertyData(
            &DEVPKEY_Device_FriendlyName,
            0, //Lcid
            0, //Flags
            0, //BufferSize
            NULL, //Buffer
            &requiredSize,
            &type
            );

    if (HRESULT_CODE(hr) != ERROR_INSUFFICIENT_BUFFER)
    {
        TraceEvents(
            TRACE_LEVEL_ERROR, 
            TEST_TRACE_DEVICE, 
            "GetPropertyData failed: hr = %!HRESULT!",
            hr
            );
        goto exit;
    }

    friendlyNameBufferSize = requiredSize;
    friendlyNameBuffer = new BYTE[requiredSize];
    if (NULL == friendlyNameBuffer)
    {
        hr = E_OUTOFMEMORY;
        TraceEvents(
            TRACE_LEVEL_ERROR, 
            TEST_TRACE_DEVICE, 
            "Out of memory while allocating property data buffer returning:”
            “ %!HRESULT!",
            hr
            );
        goto exit;
    }
    
    hr = pUnifiedPropertyStore->GetPropertyData(
            &DEVPKEY_Device_FriendlyName,
            0, //Lcid
            0, //Flags
            friendlyNameBufferSize,
            friendlyNameBuffer,
            &requiredSize,
            &type
            );

    if (FAILED(hr))
    {
        TraceEvents(
            TRACE_LEVEL_ERROR, 
            TEST_TRACE_DEVICE, 
            "GetPropertyData failed: hr = %!HRESULT!",
            hr
            );
        goto exit;
    }
    
    if (type != DEVPROP_TYPE_STRING)
    {
        TraceEvents(
            TRACE_LEVEL_ERROR, 
            TEST_TRACE_DEVICE, 
            "Expected type %d, actual type: %d",
            DEVPROP_TYPE_STRING,
            type
            );
        hr = E_UNEXPECTED;
        goto exit;
    }

exit:
    delete [] friendlyNameBuffer;
    friendlyNameBuffer = NULL;

    return hr;
}
</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfunifiedpropertystore">IWDFUnifiedPropertyStore</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfunifiedpropertystorefactory">IWDFUnifiedPropertyStoreFactory</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfunifiedpropertystorefactory-retrieveunifieddevicepropertystore">RetrieveUnifiedDevicePropertyStore</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfunifiedpropertystore-setpropertydata">SetPropertyData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi_types/ns-wudfddi_types-_wdf_property_store_root">WDF_PROPERTY_STORE_ROOT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi_types/ne-wudfddi_types-_wdf_property_store_root_class">WDF_PROPERTY_STORE_ROOT_CLASS</a>
 

 

