---
UID: NF:wudfddi.IWDFDevice.RetrieveDeviceName
title: IWDFDevice::RetrieveDeviceName (wudfddi.h)
description: The RetrieveDeviceName method retrieves the name of an underlying kernel-mode device.
old-location: wdf\iwdfdevice_retrievedevicename.htm
tech.root: wdf
ms.assetid: 75304f5d-8a07-4db5-9f20-5764ff5d2ef6
ms.date: 02/26/2018
ms.keywords: IWDFDevice interface,RetrieveDeviceName method, IWDFDevice.RetrieveDeviceName, IWDFDevice::RetrieveDeviceName, RetrieveDeviceName, RetrieveDeviceName method, RetrieveDeviceName method,IWDFDevice interface, UMDFDeviceObjectRef_6d24ee3e-719a-4408-90ea-89cc9315b8cb.xml, umdf.iwdfdevice_retrievedevicename, wdf.iwdfdevice_retrievedevicename, wudfddi/IWDFDevice::RetrieveDeviceName
ms.topic: method
f1_keywords:
 - "wudfddi/IWDFDevice.RetrieveDeviceName"
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
- IWDFDevice.RetrieveDeviceName
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFDevice::RetrieveDeviceName


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>RetrieveDeviceName</b> method retrieves the name of an underlying kernel-mode device.


## -parameters




### -param pDeviceName [out]

A pointer to a buffer that receives a <b>NULL</b>-terminated string that represents the name of the underlying kernel-mode device, if the buffer is non-<b>NULL</b> and <b>RetrieveDeviceName</b> is successful. 


### -param pdwDeviceNameLength [in, out]

A pointer to a variable that receives the number of characters, including the <b>NULL</b> character, in the device name.

If the buffer at <i>pDeviceName</i> is <b>NULL</b>, the value that the driver supplies is zero. The framework then returns the size, in characters, that is required for the device name string.

If the buffer at <i>pDeviceName</i> is non-<b>NULL</b>, the framework returns the size, in characters, of the device name string. 


## -returns



<b>RetrieveDeviceName</b> returns S_OK for the following scenarios: 


<ul>
<li>The buffer that the <i>pDeviceName</i> parameter pointed to was non-<b>NULL</b> and large enough to hold the name string, including the <b>NULL</b> character, and the framework successfully copied the string into the supplied buffer and set the variable that is pointed to by <i>pdwDeviceNameLength</i> to the number of characters in the string.</li>
<li>The buffer at <i>pDeviceName</i> was <b>NULL</b>, the driver preset the variable at <i>pdwDeviceNameLength</i> to 0, and the framework set the variable at <i>pdwDeviceNameLength</i> to the number of characters that were required for the string.</li>
</ul>


<b>RetrieveDeviceName</b> returns HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER) to indicate that the supplied buffer was non-<b>NULL</b> and did not contain enough space to hold the device name. The framework sets the variable at <i>pdwDeviceNameLength</i> to the number of characters that are required for the string.

<b>RetrieveDeviceName</b> might also return other HRESULT values.






## -remarks



The device name is not the physical device object (PDO) name. Instead, the device name is the name of the reflector. The driver must target all I/O to this device object.


#### Examples

The following code example shows how to retrieve the name of an underlying kernel-mode device.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>    PWSTR deviceName = NULL;
    DWORD deviceNameCch = 0;
    HRESULT hr;
    //
    // Get the length of the device name to allocate a buffer
    //
    hr = m_FxDevice->RetrieveDeviceName(NULL, &deviceNameCch);
    //
    // Allocate the buffer
    //
    deviceName = new WCHAR[deviceNameCch];

    if (deviceName == NULL) {
        hr = E_OUTOFMEMORY;
        goto Exit1;
    }
    //
    // Get the device name
    //
    hr = m_FxDevice->RetrieveDeviceName(deviceName,
                                        &deviceNameCch);

    // Open the device and get the handle

    m_Handle = CreateFile(deviceName, 
                         (GENERIC_READ | GENERIC_WRITE), 
                         0, 
                         NULL, 
                         OPEN_EXISTING, 
                         FILE_FLAG_OVERLAPPED, 
                         NULL);</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nn-wudfddi-iwdfdevice">IWDFDevice</a>
 

 

