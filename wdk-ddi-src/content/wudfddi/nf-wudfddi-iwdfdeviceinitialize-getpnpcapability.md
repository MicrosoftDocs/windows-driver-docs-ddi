---
UID: NF:wudfddi.IWDFDeviceInitialize.GetPnpCapability
title: IWDFDeviceInitialize::GetPnpCapability method
author: windows-driver-content
description: The GetPnpCapability method determines the state of the specified Plug and Play (PnP) capability.
old-location: wdf\iwdfdeviceinitialize_getpnpcapability.htm
old-project: wdf
ms.assetid: 64f15528-e934-4bdd-a9f7-6790eef7c7c5
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: IWDFDeviceInitialize, IWDFDeviceInitialize::GetPnpCapability, GetPnpCapability
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
req.alt-api: IWDFDeviceInitialize.GetPnpCapability
req.alt-loc: WUDFx.dll
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
req.typenames: *PPOWER_ACTION, POWER_ACTION
req.product: Windows 10 or later.
---

# IWDFDeviceInitialize::GetPnpCapability method



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetPnpCapability</b> method determines the state of the specified  Plug and Play (PnP) capability.



## -syntax

````
WDF_TRI_STATE GetPnpCapability(
  [in] WDF_PNP_CAPABILITY Capability
);
````


## -parameters

### -param Capability [in]

A <a href="..\wudfddi_types\ne-wudfddi_types-_wdf_pnp_capability.md">WDF_PNP_CAPABILITY</a>-typed value that identifies the PnP capability to retrieve status about. 


## -returns
<b>GetPnpCapability</b> returns one of the following WDF_TRI_STATE-typed values that identifies the state of the PnP capability that is specified in the <i>Capability</i> parameter:
<dl>
<dt><b>WdfUseDefault (0)</b></dt>
</dl>The capability is set to the default state.
<dl>
<dt><b>WdfFalse (1)</b></dt>
</dl>The capability is not set.
<dl>
<dt><b>WdfTrue (2)</b></dt>
</dl>The capability is set.

 


## -remarks


## -see-also
<dl>
<dt>
<a href="..\wudfddi\nn-wudfddi-iwdfdeviceinitialize.md">IWDFDeviceInitialize</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556993">IWDFDeviceInitialize::SetPnpCapability</a>
</dt>
<dt>
<a href="..\wudfddi_types\ne-wudfddi_types-_wdf_pnp_capability.md">WDF_PNP_CAPABILITY</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFDeviceInitialize::GetPnpCapability method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

