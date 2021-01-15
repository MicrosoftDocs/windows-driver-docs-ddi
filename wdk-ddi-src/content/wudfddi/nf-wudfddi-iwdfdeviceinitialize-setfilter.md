---
UID: NF:wudfddi.IWDFDeviceInitialize.SetFilter
title: IWDFDeviceInitialize::SetFilter (wudfddi.h)
description: The SetFilter method sets the property that enables a device as a filter device.
old-location: wdf\iwdfdeviceinitialize_setfilter.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["IWDFDeviceInitialize::SetFilter"]
ms.keywords: IWDFDeviceInitialize interface,SetFilter method, IWDFDeviceInitialize.SetFilter, IWDFDeviceInitialize::SetFilter, SetFilter, SetFilter method, SetFilter method,IWDFDeviceInitialize interface, UMDFDeviceObjectRef_742df830-2e67-4f03-bdfb-77cef5bc21bf.xml, umdf.iwdfdeviceinitialize_setfilter, wdf.iwdfdeviceinitialize_setfilter, wudfddi/IWDFDeviceInitialize::SetFilter
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IWDFDeviceInitialize::SetFilter
 - wudfddi/IWDFDeviceInitialize::SetFilter
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WUDFx.dll
api_name:
 - IWDFDeviceInitialize::SetFilter
---

# IWDFDeviceInitialize::SetFilter


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>SetFilter</b> method sets the property that enables a device as a filter device.

## -remarks

A filter driver calls <b>SetFilter</b> to mark itself as a filter.  When you tell the framework that your driver is a filter, the framework:

<ul>
<li>Sends  I/O requests for which the filter has not registered a callback to the next logical driver in the stack.  For example, your filter driver provides an <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iqueuecallbackdeviceiocontrol-ondeviceiocontrol">IQueueCallbackDeviceIoControl::OnDeviceIoControl</a>  method, but not <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iqueuecallbackread-onread">IQueueCallbackRead::OnRead</a> or <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iqueuecallbackwrite-onwrite">IQueueCallbackWrite::OnWrite</a>.  As a result, your filter driver receives only device I/O control requests.</li>
<li>Automatically forwards file create, cleanup, and close requests so your driver does not need to call the <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdeviceinitialize-autoforwardcreatecleanupclose">IWDFDeviceInitialize::AutoForwardCreateCleanupClose</a> method.</li>
</ul>
A driver typically calls <b>SetFilter</b> from its <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-idriverentry-ondeviceadd">IDriverEntry::OnDeviceAdd</a> method.


#### Examples

For a code example of how to use the <b>SetFilter</b> method, see <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdriver-createdevice">IWDFDriver::CreateDevice</a>.

<div class="code"></div>

## -see-also

<a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfdeviceinitialize">IWDFDeviceInitialize</a>



<a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdriver-createdevice">IWDFDriver::CreateDevice</a>

