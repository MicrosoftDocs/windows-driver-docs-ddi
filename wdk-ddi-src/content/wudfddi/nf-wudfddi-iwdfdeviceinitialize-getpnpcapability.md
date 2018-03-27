---
UID: NF:wudfddi.IWDFDeviceInitialize.GetPnpCapability
title: IWDFDeviceInitialize::GetPnpCapability method
author: windows-driver-content
description: The GetPnpCapability method determines the state of the specified Plug and Play (PnP) capability.
old-location: wdf\iwdfdeviceinitialize_getpnpcapability.htm
old-project: wdf
ms.assetid: 64f15528-e934-4bdd-a9f7-6790eef7c7c5
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GetPnpCapability method, GetPnpCapability method, IWDFDeviceInitialize interface, GetPnpCapability,IWDFDeviceInitialize.GetPnpCapability, IWDFDeviceInitialize, IWDFDeviceInitialize interface, GetPnpCapability method, IWDFDeviceInitialize::GetPnpCapability, UMDFDeviceObjectRef_1b66d13c-336f-4542-9f44-740679953603.xml, umdf.iwdfdeviceinitialize_getpnpcapability, wdf.iwdfdeviceinitialize_getpnpcapability, wudfddi/IWDFDeviceInitialize::GetPnpCapability
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
-	IWDFDeviceInitialize.GetPnpCapability
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IWDFDeviceInitialize::GetPnpCapability method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetPnpCapability</b> method determines the state of the specified  Plug and Play (PnP) capability.


## -parameters




### -param Capability [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff561428">WDF_PNP_CAPABILITY</a>-typed value that identifies the PnP capability to retrieve status about. 


## -returns



<b>GetPnpCapability</b> returns one of the following WDF_TRI_STATE-typed values that identifies the state of the PnP capability that is specified in the <i>Capability</i> parameter:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>WdfUseDefault (0)</b></dt>
</dl>
</td>
<td width="60%">
The capability is set to the default state.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>WdfFalse (1)</b></dt>
</dl>
</td>
<td width="60%">
The capability is not set.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>WdfTrue (2)</b></dt>
</dl>
</td>
<td width="60%">
The capability is set.

</td>
</tr>
</table>
 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff556965">IWDFDeviceInitialize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556993">IWDFDeviceInitialize::SetPnpCapability</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561428">WDF_PNP_CAPABILITY</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFDeviceInitialize::GetPnpCapability method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

