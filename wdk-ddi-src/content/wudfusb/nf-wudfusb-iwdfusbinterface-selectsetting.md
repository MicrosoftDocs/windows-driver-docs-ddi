---
UID: NF:wudfusb.IWDFUsbInterface.SelectSetting
title: IWDFUsbInterface::SelectSetting method
author: windows-driver-content
description: The SelectSetting method selects the specified alternate setting on a USB interface.
old-location: wdf\iwdfusbinterface_selectsetting.htm
old-project: wdf
ms.assetid: c47b025b-1be9-4fdc-965a-a9a82a394177
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: IWDFUsbInterface, wudfusb/IWDFUsbInterface::SelectSetting, UMDFUSBref_2de47773-a511-42e2-b6bb-289cc5fbebb6.xml, umdf.iwdfusbinterface_selectsetting, SelectSetting method, SelectSetting method, IWDFUsbInterface interface, IWDFUsbInterface::SelectSetting, wdf.iwdfusbinterface_selectsetting, IWDFUsbInterface interface, SelectSetting method, SelectSetting
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
-	IWDFUsbInterface.SelectSetting
product: Windows
targetos: Windows
req.typenames: WDF_USB_REQUEST_TYPE, *PWDF_USB_REQUEST_TYPE
req.product: Windows 10 or later.
---

# IWDFUsbInterface::SelectSetting method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>SelectSetting</b> method selects the specified alternate setting on a USB interface.


## -syntax


````
HRESULT SelectSetting(
  [in] UCHAR SettingNumber
);
````


## -parameters




#### - SettingNumber [in]

The setting to select on the USB interface.


## -returns


<b>SelectSetting</b> returns one of the following values: 
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK </b></dt>
</dl>
</td>
<td width="60%">

<a href="https://msdn.microsoft.com/c47b025b-1be9-4fdc-965a-a9a82a394177">SelectSetting</a> successfully selected the setting that the <i>SettingNumber</i> parameter specified. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY </b></dt>
</dl>
</td>
<td width="60%">

<a href="https://msdn.microsoft.com/c47b025b-1be9-4fdc-965a-a9a82a394177">SelectSetting</a> encountered an allocation failure.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>An error code that is defined in Winerror.h</b></dt>
</dl>
</td>
<td width="60%">
This value corresponds to the error code that the WinUsb API returned.

</td>
</tr>
</table> 



## -remarks


The framework automatically selects configuration zero, its interface zero, and the alternate setting zero. To change the alternate setting, the driver can call <b>SelectSetting</b>.

For more info <a href="https://msdn.microsoft.com/library/windows/hardware/ff539242">USB Configuration Descriptors</a>




## -see-also

<a href="..\wudfusb\nn-wudfusb-iwdfusbinterface.md">IWDFUsbInterface</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFUsbInterface::SelectSetting method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

