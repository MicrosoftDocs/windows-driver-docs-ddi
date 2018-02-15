---
UID: NF:wudfddi.IWDFDevice.RetrieveDeviceName
title: IWDFDevice::RetrieveDeviceName method
author: windows-driver-content
description: The RetrieveDeviceName method retrieves the name of an underlying kernel-mode device.
old-location: wdf\iwdfdevice_retrievedevicename.htm
old-project: wdf
ms.assetid: 75304f5d-8a07-4db5-9f20-5764ff5d2ef6
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: umdf.iwdfdevice_retrievedevicename, RetrieveDeviceName, IWDFDevice::RetrieveDeviceName, IWDFDevice interface, RetrieveDeviceName method, RetrieveDeviceName method, IWDFDevice interface, UMDFDeviceObjectRef_6d24ee3e-719a-4408-90ea-89cc9315b8cb.xml, wudfddi/IWDFDevice::RetrieveDeviceName, RetrieveDeviceName method, wdf.iwdfdevice_retrievedevicename, IWDFDevice
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
-	IWDFDevice.RetrieveDeviceName
product: Windows
targetos: Windows
req.typenames: "*PPOWER_ACTION, POWER_ACTION"
req.product: Windows 10 or later.
---

# IWDFDevice::RetrieveDeviceName method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>RetrieveDeviceName</b> method retrieves the name of an underlying kernel-mode device.


## -syntax


````
HRESULT RetrieveDeviceName(
  [out]     PWSTR pDeviceName,
  [in, out] DWORD *pdwDeviceNameLength
);
````


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
    hr = m_FxDevice-&gt;RetrieveDeviceName(NULL, &amp;deviceNameCch);
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
    hr = m_FxDevice-&gt;RetrieveDeviceName(deviceName,
                                        &amp;deviceNameCch);

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

<a href="..\wudfddi\nn-wudfddi-iwdfdevice.md">IWDFDevice</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFDevice::RetrieveDeviceName method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

