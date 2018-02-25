---
UID: NF:wudfddi.IWDFDeviceInitialize.SetPnpCapability
title: IWDFDeviceInitialize::SetPnpCapability method
author: windows-driver-content
description: The SetPnpCapability method sets the specified Plug and Play (PnP) capability of a device to the specified state.
old-location: wdf\iwdfdeviceinitialize_setpnpcapability.htm
old-project: wdf
ms.assetid: 82892740-12f6-469b-a65c-6905d32c0b0d
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: ",  , ,, ., :, C, D, F, I, IWDFDeviceInitialize, IWDFDeviceInitialize interface, SetPnpCapability method, IWDFDeviceInitialize::SetPnpCapability, P, S, SetPnpCapability method, SetPnpCapability method, IWDFDeviceInitialize interface, SetPnpCapability,IWDFDeviceInitialize.SetPnpCapability, UMDFDeviceObjectRef_516aeba5-c0c2-40a0-a9e6-d1a983835a94.xml, W, a, b, c, e, i, l, n, p, t, umdf.iwdfdeviceinitialize_setpnpcapability, v, wdf.iwdfdeviceinitialize_setpnpcapability, wudfddi/IWDFDeviceInitialize::SetPnpCapability, y, z"
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
-	IWDFDeviceInitialize.SetPnpCapability
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IWDFDeviceInitialize::SetPnpCapability method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>SetPnpCapability</b> method sets the specified Plug and Play (PnP) capability of a device to the specified state.


## -syntax


````
void SetPnpCapability(
  [in] WDF_PNP_CAPABILITY Capability,
  [in] WDF_TRI_STATE      Value
);
````


## -parameters




### -param Capability [in]

A <a href="..\wudfddi_types\ne-wudfddi_types-_wdf_pnp_capability.md">WDF_PNP_CAPABILITY</a>-typed value that identifies the PnP capability to set. 


### -param Value [in]

A WDF_TRI_STATE-typed value that identifies how to set the PnP capability that is specified by <i>Capability</i>. The following table shows the possible values.

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
Set the capability to the default state.

</td>
</tr>
<tr>
<td>
<b>WdfFalse</b> (1)

</td>
<td>
Do not set the capability.

</td>
</tr>
<tr>
<td>
<b>WdfTrue</b> (2)

</td>
<td>
Set the capability.

</td>
</tr>
</table>
 


## -returns



None




## -see-also

<a href="..\wudfddi_types\ne-wudfddi_types-_wdf_pnp_capability.md">WDF_PNP_CAPABILITY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556974">IWDFDeviceInitialize::GetPnpCapability</a>



<a href="..\wudfddi\nn-wudfddi-iwdfdeviceinitialize.md">IWDFDeviceInitialize</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFDeviceInitialize::SetPnpCapability method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

