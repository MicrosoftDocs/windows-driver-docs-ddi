---
UID: NF:wudfusb.IWDFUsbTargetDevice.GetNumInterfaces
title: IWDFUsbTargetDevice::GetNumInterfaces method
author: windows-driver-content
description: The GetNumInterfaces method retrieves the number of USB interfaces for the USB device.
old-location: wdf\iwdfusbtargetdevice_getnuminterfaces.htm
old-project: wdf
ms.assetid: 4da2f2b0-f2ad-465d-b63e-f11406d4c210
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: GetNumInterfaces method, IWDFUsbTargetDevice interface, umdf.iwdfusbtargetdevice_getnuminterfaces, IWDFUsbTargetDevice interface, GetNumInterfaces method, GetNumInterfaces method, UMDFUSBref_43f488a1-350d-473a-aa10-d88983ea39f7.xml, GetNumInterfaces, IWDFUsbTargetDevice, wudfusb/IWDFUsbTargetDevice::GetNumInterfaces, wdf.iwdfusbtargetdevice_getnuminterfaces, IWDFUsbTargetDevice::GetNumInterfaces
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfusb.h
req.include-header: Wudfusb.h
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
req.lib: wudfusb.h
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
-	IWDFUsbTargetDevice.GetNumInterfaces
product: Windows
targetos: Windows
req.typenames: "*PWDF_USB_REQUEST_TYPE, WDF_USB_REQUEST_TYPE"
req.product: Windows 10 or later.
---

# IWDFUsbTargetDevice::GetNumInterfaces method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetNumInterfaces</b> method retrieves the number of USB interfaces for the USB device.


## -syntax


````
UCHAR GetNumInterfaces();
````


## -parameters






## -returns



<b>GetNumInterfaces</b> returns the number of <a href="..\wudfusb\nn-wudfusb-iwdfusbinterface.md">IWDFUsbInterface</a> interfaces for the USB device in the default configuration. The default configuration is identified by index zero.




## -remarks



UMDF USB I/O target devices do not support multiple configurations. 


#### Examples

The following code example retrieves the number of USB interfaces for the USB device.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>    UCHAR NumInterfaces = pIUsbTargetDevice-&gt;GetNumInterfaces();</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wudfusb\nn-wudfusb-iwdfusbinterface.md">IWDFUsbInterface</a>



<a href="..\wudfusb\nn-wudfusb-iwdfusbtargetdevice.md">IWDFUsbTargetDevice</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFUsbTargetDevice::GetNumInterfaces method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

