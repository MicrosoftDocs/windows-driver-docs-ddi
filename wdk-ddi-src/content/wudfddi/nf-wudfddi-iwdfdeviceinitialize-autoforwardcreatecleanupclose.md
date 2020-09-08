---
UID: NF:wudfddi.IWDFDeviceInitialize.AutoForwardCreateCleanupClose
title: IWDFDeviceInitialize::AutoForwardCreateCleanupClose (wudfddi.h)
description: The AutoForwardCreateCleanupClose method controls when create, cleanup, and close notifications are forwarded to the next lower driver in the device stack.
old-location: wdf\iwdfdeviceinitialize_autoforwardcreatecleanupclose.htm
tech.root: wdf
ms.assetid: b9c8e54e-7cd5-48a9-b948-5327900c8a99
ms.date: 02/26/2018
keywords: ["IWDFDeviceInitialize::AutoForwardCreateCleanupClose"]
ms.keywords: AutoForwardCreateCleanupClose, AutoForwardCreateCleanupClose method, AutoForwardCreateCleanupClose method,IWDFDeviceInitialize interface, IWDFDeviceInitialize interface,AutoForwardCreateCleanupClose method, IWDFDeviceInitialize.AutoForwardCreateCleanupClose, IWDFDeviceInitialize::AutoForwardCreateCleanupClose, UMDFDeviceObjectRef_6f68d9cd-cfb9-49ae-94b8-a230e4dc0762.xml, umdf.iwdfdeviceinitialize_autoforwardcreatecleanupclose, wdf.iwdfdeviceinitialize_autoforwardcreatecleanupclose, wudfddi/IWDFDeviceInitialize::AutoForwardCreateCleanupClose
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
 - IWDFDeviceInitialize::AutoForwardCreateCleanupClose
 - wudfddi/IWDFDeviceInitialize::AutoForwardCreateCleanupClose
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WUDFx.dll
api_name:
 - IWDFDeviceInitialize.AutoForwardCreateCleanupClose
---

# IWDFDeviceInitialize::AutoForwardCreateCleanupClose


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>AutoForwardCreateCleanupClose</b> method controls when create, cleanup, and close notifications are forwarded to the next lower driver in the device stack.

## -parameters

### -param State 

[in]
A WDF_TRI_STATE-typed value that identifies the state of automatic forwarding. The following table shows the possible values.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<b>WdfUseDefault</b> (0)

</td>
<td>
The framework uses the default forwarding scheme. For more information, see the following Remarks section.

</td>
</tr>
<tr>
<td>
<b>WdfFalse</b> (1)

</td>
<td>
The framework does not forward create, cleanup, and close notifications to the next lower driver.

</td>
</tr>
<tr>
<td>
<b>WdfTrue</b> (2)

</td>
<td>
The framework synchronously forwards create, cleanup, and close notifications to the next lower driver.

</td>
</tr>
</table>

## -remarks

If the UMDF driver passes <b>WdfUseDefault</b> for the <i>State</i> parameter in a call to <b>AutoForwardCreateCleanupClose</b>, the framework uses a default forwarding scheme for create, cleanup, and close notifications that depends on whether the driver is a filter or function driver:

<ul>
<li>
If the driver is a filter driver, the default forwarding scheme is to synchronously forward notifications to the next lower driver.

</li>
<li>
If the driver is a function driver, the default forwarding scheme is not to forward notifications to the next lower driver.

</li>
</ul>
If the framework is set up for forwarding, it forwards cleanup and close notifications regardless of whether the driver supports the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-ifilecallbackcleanup-oncleanupfile">IFileCallbackCleanup::OnCleanupFile</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-ifilecallbackclose-onclosefile">IFileCallbackClose::OnCloseFile</a> interface methods. However, the framework automatically forwards create requests only if the driver does not support the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iqueuecallbackcreate-oncreatefile">IQueueCallbackCreate::OnCreateFile</a> method. If the driver supports <b>IQueueCallbackCreate::OnCreateFile</b>, the framework forwards create requests only if the driver explicitly set up forwarding (<b>WdfTrue</b>) to the next lower driver. 

For more information about how a UMDF driver uses <b>AutoForwardCreateCleanupClose</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/preventing-an-imbalance-of-create-and-close-notifications-to-a-driver">Preventing an Imbalance of Create and Close Notifications to a Driver</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-ifilecallbackcleanup-oncleanupfile">IFileCallbackCleanup::OnCleanupFile</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-ifilecallbackclose-onclosefile">IFileCallbackClose::OnCloseFile</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iqueuecallbackcreate-oncreatefile">IQueueCallbackCreate::OnCreateFile</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfdeviceinitialize">IWDFDeviceInitialize</a>

