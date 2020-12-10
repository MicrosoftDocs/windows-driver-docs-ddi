---
UID: NF:wudfddi.IWDFDeviceInitialize.GetPnpCapability
title: IWDFDeviceInitialize::GetPnpCapability (wudfddi.h)
description: The GetPnpCapability method determines the state of the specified Plug and Play (PnP) capability.
old-location: wdf\iwdfdeviceinitialize_getpnpcapability.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["IWDFDeviceInitialize::GetPnpCapability"]
ms.keywords: GetPnpCapability, GetPnpCapability method, GetPnpCapability method,IWDFDeviceInitialize interface, IWDFDeviceInitialize interface,GetPnpCapability method, IWDFDeviceInitialize.GetPnpCapability, IWDFDeviceInitialize::GetPnpCapability, UMDFDeviceObjectRef_1b66d13c-336f-4542-9f44-740679953603.xml, umdf.iwdfdeviceinitialize_getpnpcapability, wdf.iwdfdeviceinitialize_getpnpcapability, wudfddi/IWDFDeviceInitialize::GetPnpCapability
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
 - IWDFDeviceInitialize::GetPnpCapability
 - wudfddi/IWDFDeviceInitialize::GetPnpCapability
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WUDFx.dll
api_name:
 - IWDFDeviceInitialize.GetPnpCapability
---

# IWDFDeviceInitialize::GetPnpCapability


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetPnpCapability</b> method determines the state of the specified  Plug and Play (PnP) capability.

## -parameters

### -param Capability 

[in]
A <a href="/windows-hardware/drivers/ddi/wudfddi_types/ne-wudfddi_types-_wdf_pnp_capability">WDF_PNP_CAPABILITY</a>-typed value that identifies the PnP capability to retrieve status about.

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

<a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfdeviceinitialize">IWDFDeviceInitialize</a>



<a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdeviceinitialize-setpnpcapability">IWDFDeviceInitialize::SetPnpCapability</a>



<a href="/windows-hardware/drivers/ddi/wudfddi_types/ne-wudfddi_types-_wdf_pnp_capability">WDF_PNP_CAPABILITY</a>
