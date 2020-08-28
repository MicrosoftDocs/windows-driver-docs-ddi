---
UID: NF:wudfddi.IPowerPolicyCallbackWakeFromS0.OnWakeFromS0Triggered
title: IPowerPolicyCallbackWakeFromS0::OnWakeFromS0Triggered (wudfddi.h)
description: A driver's OnWakeFromS0Triggered event callback function informs the driver that its device, which had previously entered a low-power device state while the system power state remained at S0, might have triggered a wake signal.
old-location: wdf\ipowerpolicycallbackwakefroms0_onwakefroms0triggered.htm
tech.root: wdf
ms.assetid: ebcd31f9-79cd-4c43-8cac-231ff97f269e
ms.date: 02/26/2018
keywords: ["IPowerPolicyCallbackWakeFromS0::OnWakeFromS0Triggered"]
ms.keywords: IPowerPolicyCallbackWakeFromS0 interface,OnWakeFromS0Triggered method, IPowerPolicyCallbackWakeFromS0.OnWakeFromS0Triggered, IPowerPolicyCallbackWakeFromS0::OnWakeFromS0Triggered, OnWakeFromS0Triggered, OnWakeFromS0Triggered method, OnWakeFromS0Triggered method,IPowerPolicyCallbackWakeFromS0 interface, UMDFDeviceObjectRef_52f89758-227c-4849-83ac-30826d2d36d0.xml, umdf.ipowerpolicycallbackwakefroms0_onwakefroms0triggered, wdf.ipowerpolicycallbackwakefroms0_onwakefroms0triggered, wudfddi/IPowerPolicyCallbackWakeFromS0::OnWakeFromS0Triggered
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
 - IPowerPolicyCallbackWakeFromS0::OnWakeFromS0Triggered
 - wudfddi/IPowerPolicyCallbackWakeFromS0::OnWakeFromS0Triggered
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Wudfddi.h
api_name:
 - IPowerPolicyCallbackWakeFromS0.OnWakeFromS0Triggered
---

# IPowerPolicyCallbackWakeFromS0::OnWakeFromS0Triggered


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

A driver's <b>OnWakeFromS0Triggered</b> event callback function informs the driver that its device, which had previously entered a low-power device state while the system power state remained at S0, might have triggered a wake signal.

## -parameters

### -param pWdfDevice 

[in]
A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfdevice">IWDFDevice</a> interface of the device object that represents one of the driver's devices.

## -remarks

Your driver must provide an <b>OnWakeFromS0Triggered</b> callback function if the driver supports the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-ipowerpolicycallbackwakefroms0">IPowerPolicyCallbackWakeFromS0</a> interface. 

If the driver provides this callback function, the framework calls the function after it calls the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-ipnpcallback-ond0entry">IPnpCallback::OnD0Entry</a> callback function and before it calls the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-ipowerpolicycallbackwakefroms0-ondisarmwakefroms0">IPowerPolicyCallbackWakeFromS0::OnDisarmWakeFromS0</a> callback function.

System hardware (BIOSes, motherboards, bus adapters) can sometimes drop a wake signal before the bus driver detects it, even though the signal wakes up the system. In such cases, the driver's <b>OnWakeFromS0Triggered</b> callback function will not be called even though the driver's device triggered a wake signal.

For more information about this callback function, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/supporting-idle-power-down-in-umdf-drivers">Supporting Idle Power-Down in UMDF-based Drivers</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-ipowerpolicycallbackwakefroms0">IPowerPolicyCallbackWakeFromS0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-ipowerpolicycallbackwakefroms0-onarmwakefroms0">IPowerPolicyCallbackWakeFromS0::OnArmWakeFromS0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-ipowerpolicycallbackwakefroms0-ondisarmwakefroms0">IPowerPolicyCallbackWakeFromS0::OnDisarmWakeFromS0</a>

