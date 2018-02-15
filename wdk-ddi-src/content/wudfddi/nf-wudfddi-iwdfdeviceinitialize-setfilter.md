---
UID: NF:wudfddi.IWDFDeviceInitialize.SetFilter
title: IWDFDeviceInitialize::SetFilter method
author: windows-driver-content
description: The SetFilter method sets the property that enables a device as a filter device.
old-location: wdf\iwdfdeviceinitialize_setfilter.htm
old-project: wdf
ms.assetid: a5f61a83-43db-4ad7-9b18-0cdf574ea546
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: IWDFDeviceInitialize interface, SetFilter method, wdf.iwdfdeviceinitialize_setfilter, SetFilter method, IWDFDeviceInitialize interface, IWDFDeviceInitialize, SetFilter method, wudfddi/IWDFDeviceInitialize::SetFilter, SetFilter, IWDFDeviceInitialize::SetFilter, umdf.iwdfdeviceinitialize_setfilter, UMDFDeviceObjectRef_742df830-2e67-4f03-bdfb-77cef5bc21bf.xml
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
-	IWDFDeviceInitialize.SetFilter
product: Windows
targetos: Windows
req.typenames: "*PPOWER_ACTION, POWER_ACTION"
req.product: Windows 10 or later.
---

# IWDFDeviceInitialize::SetFilter method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>SetFilter</b> method sets the property that enables a device as a filter device.


## -syntax


````
void SetFilter();
````


## -parameters






## -returns



None




## -remarks



A filter driver calls <b>SetFilter</b> to mark itself as a filter.  When you tell the framework that your driver is a filter, the framework:

<ul>
<li>Sends  I/O requests for which the filter has not registered a callback to the next logical driver in the stack.  For example, your filter driver provides an <a href="https://msdn.microsoft.com/library/windows/hardware/ff556854">IQueueCallbackDeviceIoControl::OnDeviceIoControl</a>  method, but not <a href="https://msdn.microsoft.com/library/windows/hardware/ff556875">IQueueCallbackRead::OnRead</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff556885">IQueueCallbackWrite::OnWrite</a>.  As a result, your filter driver receives only device I/O control requests.</li>
<li>Automatically forwards file create, cleanup, and close requests so your driver does not need to call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556971">IWDFDeviceInitialize::AutoForwardCreateCleanupClose</a> method.</li>
</ul>
A driver typically calls <b>SetFilter</b> from its <a href="https://msdn.microsoft.com/library/windows/hardware/ff554896">IDriverEntry::OnDeviceAdd</a> method.


#### Examples

For a code example of how to use the <b>SetFilter</b> method, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558899">IWDFDriver::CreateDevice</a>.

<div class="code"></div>



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff558899">IWDFDriver::CreateDevice</a>



<a href="..\wudfddi\nn-wudfddi-iwdfdeviceinitialize.md">IWDFDeviceInitialize</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFDeviceInitialize::SetFilter method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

