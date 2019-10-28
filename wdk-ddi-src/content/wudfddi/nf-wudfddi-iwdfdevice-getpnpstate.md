---
UID: NF:wudfddi.IWDFDevice.GetPnpState
title: IWDFDevice::GetPnpState (wudfddi.h)
description: The GetPnpState method determines whether the given Plug and Play (PnP) property of a device is on or off (or set to the default state).
old-location: wdf\iwdfdevice_getpnpstate.htm
tech.root: wdf
ms.assetid: 7214a0e9-5519-4daa-bd2f-cc3c697dd867
ms.date: 02/26/2018
ms.keywords: GetPnpState, GetPnpState method, GetPnpState method,IWDFDevice interface, IWDFDevice interface,GetPnpState method, IWDFDevice.GetPnpState, IWDFDevice::GetPnpState, UMDFDeviceObjectRef_6fe8971d-2af6-4fc0-a902-74edb5d45f39.xml, umdf.iwdfdevice_getpnpstate, wdf.iwdfdevice_getpnpstate, wudfddi/IWDFDevice::GetPnpState
ms.topic: method
f1_keywords:
 - "wudfddi/IWDFDevice.GetPnpState"
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- WUDFx.dll
api_name:
- IWDFDevice.GetPnpState
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFDevice::GetPnpState


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetPnpState</b> method determines whether the given Plug and Play (PnP) property of a device is on or off (or set to the default state).


## -parameters




### -param State [in]

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi_types/ne-wudfddi_types-_wdf_pnp_state">WDF_PNP_STATE</a>-typed value that identifies the PnP property to retrieve status about. 


## -returns



<b>GetPnpState</b> returns one of the following WDF_TRI_STATE-typed values that identifies the state of the PnP property that is specified in the <i>State</i> parameter.

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
The PnP property is set to the default state.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>WdfFalse (1)</b></dt>
</dl>
</td>
<td width="60%">
The PnP property is turned off.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>WdfTrue (2)</b></dt>
</dl>
</td>
<td width="60%">
The PnP property is turned on.

</td>
</tr>
</table>
 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfdevice">IWDFDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice-setpnpstate">IWDFDevice::SetPnpState</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi_types/ne-wudfddi_types-_wdf_pnp_state">WDF_PNP_STATE</a>
 

 

