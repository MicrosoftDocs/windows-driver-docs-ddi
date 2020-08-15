---
UID: NF:wudfddi.IWDFDevice2.CreateSymbolicLinkWithReferenceString
title: IWDFDevice2::CreateSymbolicLinkWithReferenceString (wudfddi.h)
description: TheCreateSymbolicLinkWithReferenceString method creates a symbolic link name, and optionally, a reference string, for a device.
old-location: wdf\iwdfdevice2_createsymboliclinkwithreferencestring.htm
tech.root: wdf
ms.assetid: bce932a6-2f73-4d0e-8616-45fd41abb776
ms.date: 02/26/2018
keywords: ["IWDFDevice2::CreateSymbolicLinkWithReferenceString"]
ms.keywords: CreateSymbolicLinkWithReferenceString, CreateSymbolicLinkWithReferenceString method, CreateSymbolicLinkWithReferenceString method,IWDFDevice2 interface, IWDFDevice2 interface,CreateSymbolicLinkWithReferenceString method, IWDFDevice2.CreateSymbolicLinkWithReferenceString, IWDFDevice2::CreateSymbolicLinkWithReferenceString, UMDFDeviceObjectRef_40f806fa-5db7-48db-b3c7-0f338947887e.xml, umdf.iwdfdevice2_createsymboliclinkwithreferencestring, wdf.iwdfdevice2_createsymboliclinkwithreferencestring, wudfddi/IWDFDevice2::CreateSymbolicLinkWithReferenceString
f1_keywords:
 - "wudfddi/IWDFDevice2.CreateSymbolicLinkWithReferenceString"
 - "IWDFDevice2.CreateSymbolicLinkWithReferenceString"
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
- IWDFDevice2.CreateSymbolicLinkWithReferenceString
targetos: Windows
req.typenames: 
---

# IWDFDevice2::CreateSymbolicLinkWithReferenceString


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The<b>CreateSymbolicLinkWithReferenceString</b> method creates a symbolic link name, and optionally, a reference string, for a device 


## -parameters




### -param pSymbolicLink 
[in]
A pointer to a <b>NULL</b>-terminated character string that becomes the user-visible name of the device. The symbolic link name must be in the global <b>DosDevices</b> namespace.


### -param pReferenceString 
[in, optional]
A pointer to a <b>NULL</b>-terminated character string that Windows appends to the device name when an application uses the symbolic name that the <i>pSymbolicLink</i> parameter specifies. For more information, see the following Remarks section. This parameter is optional and can be <b>NULL</b>.


## -returns



<b>CreateSymbolicLinkWithReferenceString</b> returns S_OK if the operation succeeds. Otherwise, the method might return one of the following values:

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
The caller specified an invalid value for an input parameter.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">
The memory allocation failed.

</td>
</tr>
</table>
 

This method might return one of the other values that Winerror.h contains.




## -remarks



<b>CreateSymbolicLinkWithReferenceString</b> creates a symbolic link name, and optionally a reference string, for the device that the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfdevice2">IWDFDevice2</a> interface represents. After a driver calls <b>CreateSymbolicLinkWithReferenceString</b>, applications can use the symbolic link name to access the device.

Suppose your device's name is "\Device\MyDevice". You can create a symbolic link name of "DeviceUserName" for your device by specifying "L"DeviceUserName"" for the <i>pSymbolicLink</i> parameter. If you specify "L"Instance3"" for the <i>pReferenceString</i> parameter, you are creating a symbolic link to \Device\MyDevice\Instance3. If an application opens the device by using the symbolic link name, the I/O manager opens \Device\MyDevice and creates a WDM file object that contains the \Instance3 string as the file name. Your UMDF-based driver receives a framework-created file object, which also contains the \Instance3 string as the file name (see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdffile-retrievefilename">IWDFFile::RetrieveFileName</a>). 

Typically, instead of providing symbolic links, framework-based drivers provide <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice-createdeviceinterface">device interfaces</a> that applications can use to access their devices.

If the device is removed unexpectedly (surprise-removed), the framework removes the symbolic link to the device. The driver can then use the symbolic link name for a new instance of the device. 

If you do not need to add a reference string to your device's symbolic link name, your driver can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice-createsymboliclink">IWDFDevice::CreateSymbolicLink</a> instead of <b>CreateSymbolicLinkWithReferenceString</b>.


#### Examples


          The following line defines a symbolic link name prefix in the global <b>DosDevices</b> namespace.
        

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>#define SYMBOLIC_LINK_NAME_PREFIX   L"\\DosDevices\\Global\\"</pre>
</td>
</tr>
</table></span></div>
The following code example creates a symbolic name string, obtains the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfdevice2">IWDFDevice2</a> interface, and then calls <b>CreateSymbolicLinkWithReferenceString</b>.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>
    IWDFDevice2 *pDevice2 = NULL;
    HRESULT hr;

    //
    // Create symbolic link name string.
    //
    hr = StringCchPrintf(portFullName,
                         portFullNameLength,
                         L"%ws%ws",
                         SYMBOLIC_LINK_NAME_PREFIX,
                         portName);
    if (FAILED(hr))
    {
        goto Exit;
    }

    //
    // Get a pointer to the IWDFDevice2 interface.
    //
    hr = pIWDFDevice->QueryInterface(__uuidof(IWDFDevice2),
                                     (void**) &pDevice2);
    if (SUCCEEDED(hr)) 
    {
    hr = pDevice2->CreateSymbolicLinkWithReferenceString(portFullName,
                                                         portCountString);
    if (FAILED(hr))
        {
            goto Exit;
        }
        SAFE_RELEASE(pDevice2);
    }</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfdevice2">IWDFDevice2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice-createsymboliclink">IWDFDevice::CreateSymbolicLink</a>
 

 

