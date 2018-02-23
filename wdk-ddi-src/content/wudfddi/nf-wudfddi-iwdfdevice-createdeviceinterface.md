---
UID: NF:wudfddi.IWDFDevice.CreateDeviceInterface
title: IWDFDevice::CreateDeviceInterface method
author: windows-driver-content
description: The CreateDeviceInterface method creates an instance of a device interface class.
old-location: wdf\iwdfdevice_createdeviceinterface.htm
old-project: wdf
ms.assetid: 0a88cbb6-66be-4ef7-93da-27d7ce169779
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: IWDFDevice interface, CreateDeviceInterface method, wdf.iwdfdevice_createdeviceinterface, CreateDeviceInterface method, IWDFDevice interface, wudfddi/IWDFDevice::CreateDeviceInterface, umdf.iwdfdevice_createdeviceinterface, CreateDeviceInterface, IWDFDevice::CreateDeviceInterface, CreateDeviceInterface method, UMDFDeviceObjectRef_11606922-8b72-434f-a739-fd0c653ea026.xml, IWDFDevice
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
-	IWDFDevice.CreateDeviceInterface
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IWDFDevice::CreateDeviceInterface method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>CreateDeviceInterface</b> method creates an instance of a device interface class.


## -syntax


````
HRESULT CreateDeviceInterface(
  [in]           LPCGUID pDeviceInterfaceGuid,
  [in, optional] PCWSTR  pReferenceString
);
````


## -parameters




### -param pDeviceInterfaceGuid [in]

A pointer to the GUID for a device interface class.


### -param pReferenceString [in, optional]

A pointer to a <b>NULL</b>-terminated string that contains the name of the instance of the device interface. This parameter is optional. The driver can pass <b>NULL</b> if the driver does not have to supply a name. If the driver must supply a name, the string that the driver passes must not contain any path separator characters ("/" or "\"). 


## -returns



<b>CreateDeviceInterface</b> returns S_OK if the operation succeeds. Otherwise, this method returns one of the error codes that are defined in Winerror.h.




## -remarks



Drivers can use the <i>pReferenceString</i> parameter to differentiate different instances of a single interface. In other words, if a driver calls <b>CreateDeviceInterface</b> twice for the same device interface class, the driver can specify a different string for <i>pReferenceString</i> each time. When an instance of an interface is opened, the framework passes the instance's reference string to the driver. The reference string is appended to the path component of the interface instance's name. The driver can then use the reference string to determine which instance of the device interface class is being opened.

If <b>CreateDeviceInterface</b> succeeds, the initial state of the interface is disabled. If creation succeeds, the framework automatically enables and disables the interface based on the device's PnP state.  In addition, a driver can disable and re-enable a device interface as necessary by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff557006">IWDFDevice::AssignDeviceInterfaceState</a>.

For more information about device interfaces, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-device-interfaces-in-umdf-drivers">Using Device Interfaces in UMDF-based Drivers</a>.


#### Examples

The following code example shows how to create a device interface instance. In this example, the driver explicitly calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff557006">IWDFDevice::AssignDeviceInterfaceState</a> to enable the interface.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>    //
    // Create the device interface.
    //
    HRESULT hr;
    if (S_OK == hr) {
        hr = m_FxDevice-&gt;CreateDeviceInterface(
                         &amp;GUID_DEVINTERFACE_OSRUSBFX2,
                         NULL);
    }
    if (S_OK == hr) {
        hr = m_FxDevice-&gt;AssignDeviceInterfaceState(
                        &amp;GUID_DEVINTERFACE_OSRUSBFX2,
                        NULL,
                        TRUE);
    }</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wudfddi\nn-wudfddi-iwdfdevice.md">IWDFDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557006">IWDFDevice::AssignDeviceInterfaceState</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFDevice::CreateDeviceInterface method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

