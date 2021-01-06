---
UID: NF:wudfddi.IPowerPolicyCallbackWakeFromS0.OnDisarmWakeFromS0
title: IPowerPolicyCallbackWakeFromS0::OnDisarmWakeFromS0 (wudfddi.h)
description: A driver's OnDisarmWakeFromS0 event callback function disarms (that is, disables) a device's ability to trigger a wake signal while in a low-power device state, if the system remains in the system working state (S0).
old-location: wdf\ipowerpolicycallbackwakefroms0_ondisarmwakefroms0.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["IPowerPolicyCallbackWakeFromS0::OnDisarmWakeFromS0"]
ms.keywords: IPowerPolicyCallbackWakeFromS0 interface,OnDisarmWakeFromS0 method, IPowerPolicyCallbackWakeFromS0.OnDisarmWakeFromS0, IPowerPolicyCallbackWakeFromS0::OnDisarmWakeFromS0, OnDisarmWakeFromS0, OnDisarmWakeFromS0 method, OnDisarmWakeFromS0 method,IPowerPolicyCallbackWakeFromS0 interface, UMDFDeviceObjectRef_f12fda31-6979-43bf-af04-e46814728ed4.xml, umdf.ipowerpolicycallbackwakefroms0_ondisarmwakefroms0, wdf.ipowerpolicycallbackwakefroms0_ondisarmwakefroms0, wudfddi/IPowerPolicyCallbackWakeFromS0::OnDisarmWakeFromS0
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.9
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - IPowerPolicyCallbackWakeFromS0::OnDisarmWakeFromS0
 - wudfddi/IPowerPolicyCallbackWakeFromS0::OnDisarmWakeFromS0
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Wudfddi.h
api_name:
 - IPowerPolicyCallbackWakeFromS0.OnDisarmWakeFromS0
---

# IPowerPolicyCallbackWakeFromS0::OnDisarmWakeFromS0


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

A driver's <b>OnDisarmWakeFromS0</b> event callback function disarms (that is, disables) a device's ability to trigger a wake signal while in a low-power device state, if the system remains in the <a href="/windows-hardware/drivers/kernel/system-working-state-s0">system working state</a> (S0).

## -parameters

### -param pWdfDevice 

[in]
A pointer to the <a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfdevice">IWDFDevice</a> interface of the device object that represents one of the driver's devices.

## -remarks

Your driver must provide an <b>OnDisarmWakeFromS0</b> callback function if the driver supports the <a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-ipowerpolicycallbackwakefroms0">IPowerPolicyCallbackWakeFromS0</a> interface. 

If the driver provides an <b>OnDisarmWakeFromS0</b> callback function, the framework calls it after the bus driver determines that an event has awakened the device, and after the bus driver subsequently completes the <a href="/windows-hardware/drivers/kernel/sending-a-wait-wake-irp">wait/wake IRP</a>. Before calling the driver's <b>OnDisarmWakeFromS0</b> callback function, the framework calls the driver's <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-ipnpcallback-ond0entry">IPnpCallback::OnD0Entry</a> and <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-ipowerpolicycallbackwakefroms0-onwakefroms0triggered">IPowerPolicyCallbackWakeFromS0::OnWakeFromS0Triggered</a> callback functions.

The <b>OnDisarmWakeFromS0</b> callback function must perform any hardware operations that are needed to disable the device's ability to trigger a wake signal after the power is lowered.

For more information about when the framework calls this callback function, see <a href="/windows-hardware/drivers/wdf/pnp-and-power-management-scenarios-in-umdf">PnP and Power Management Scenarios in UMDF</a>.

For more information about this callback function, see <a href="/windows-hardware/drivers/wdf/supporting-idle-power-down-in-umdf-drivers">Supporting Idle Power-Down in UMDF-based Drivers</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-ipowerpolicycallbackwakefroms0">IPowerPolicyCallbackWakeFromS0</a>



<a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-ipowerpolicycallbackwakefroms0-onarmwakefroms0">IPowerPolicyCallbackWakeFromS0::OnArmWakeFromS0</a>



<a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-ipowerpolicycallbackwakefroms0-onwakefroms0triggered">IPowerPolicyCallbackWakeFromS0::OnWakeFromS0Triggered</a>
