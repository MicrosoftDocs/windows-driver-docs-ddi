---
UID: NF:wudfusb.IWDFUsbTargetDevice.GetNumInterfaces
title: IWDFUsbTargetDevice::GetNumInterfaces
author: windows-driver-content
description: The GetNumInterfaces method retrieves the number of USB interfaces for the USB device.
old-location: wdf\iwdfusbtargetdevice_getnuminterfaces.htm
old-project: wdf
ms.assetid: 4da2f2b0-f2ad-465d-b63e-f11406d4c210
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GetNumInterfaces, GetNumInterfaces method, GetNumInterfaces method,IWDFUsbTargetDevice interface, IWDFUsbTargetDevice interface,GetNumInterfaces method, IWDFUsbTargetDevice.GetNumInterfaces, IWDFUsbTargetDevice::GetNumInterfaces, UMDFUSBref_43f488a1-350d-473a-aa10-d88983ea39f7.xml, umdf.iwdfusbtargetdevice_getnuminterfaces, wdf.iwdfusbtargetdevice_getnuminterfaces, wudfusb/IWDFUsbTargetDevice::GetNumInterfaces
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
-	IWDFUsbTargetDevice.GetNumInterfaces
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFUsbTargetDevice::GetNumInterfaces


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetNumInterfaces</b> method retrieves the number of USB interfaces for the USB device.


## -parameters






## -returns



<b>GetNumInterfaces</b> returns the number of <a href="https://msdn.microsoft.com/library/windows/hardware/ff560312">IWDFUsbInterface</a> interfaces for the USB device in the default configuration. The default configuration is identified by index zero.




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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560312">IWDFUsbInterface</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560362">IWDFUsbTargetDevice</a>
 

 

