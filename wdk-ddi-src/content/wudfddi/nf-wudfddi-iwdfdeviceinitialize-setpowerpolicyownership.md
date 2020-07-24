---
UID: NF:wudfddi.IWDFDeviceInitialize.SetPowerPolicyOwnership
title: IWDFDeviceInitialize::SetPowerPolicyOwnership (wudfddi.h)
description: The SetPowerPolicyOwnership method sets the ownership of the power policy to a driver or removes ownership from the driver.
old-location: wdf\iwdfdeviceinitialize_setpowerpolicyownership.htm
tech.root: wdf
ms.assetid: 18b0b277-97c8-4aff-9f09-34822ce84290
ms.date: 02/26/2018
keywords: ["IWDFDeviceInitialize::SetPowerPolicyOwnership"]
ms.keywords: IWDFDeviceInitialize interface,SetPowerPolicyOwnership method, IWDFDeviceInitialize.SetPowerPolicyOwnership, IWDFDeviceInitialize::SetPowerPolicyOwnership, SetPowerPolicyOwnership, SetPowerPolicyOwnership method, SetPowerPolicyOwnership method,IWDFDeviceInitialize interface, UMDFDeviceObjectRef_849680d0-e616-4862-9c59-50150f6c15f0.xml, umdf.iwdfdeviceinitialize_setpowerpolicyownership, wdf.iwdfdeviceinitialize_setpowerpolicyownership, wudfddi/IWDFDeviceInitialize::SetPowerPolicyOwnership
f1_keywords:
 - "wudfddi/IWDFDeviceInitialize.SetPowerPolicyOwnership"
 - "IWDFDeviceInitialize.SetPowerPolicyOwnership"
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
- IWDFDeviceInitialize.SetPowerPolicyOwnership
targetos: Windows
req.typenames: 
---

# IWDFDeviceInitialize::SetPowerPolicyOwnership


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>SetPowerPolicyOwnership</b> method sets the ownership of the power policy to a driver or removes ownership from the driver.


## -parameters




### -param fTrue [in]

A BOOL value that specifies whether to set power-policy ownership to the driver or remove ownership from the driver. <b>TRUE</b> indicates to set power-policy ownership to the driver; <b>FALSE</b> indicates to remove ownership from the driver.


## -remarks



By default, UMDF drivers are not registered as power-policy owners for their device stack. To register itself as the power-policy owner for its device stack, a UMDF driver must explicitly call <b>SetPowerPolicyOwnership</b> and pass <b>TRUE</b> to the <i>fTrue</i> parameter in this call.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/power-policy-ownership-in-umdf">Power Policy Ownership in UMDF</a>.


#### Examples

For a code example of how to use the <b>SetPowerPolicyOwnership</b> method, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdriver-createdevice">IWDFDriver::CreateDevice</a>.

<div class="code"></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfdeviceinitialize">IWDFDeviceInitialize</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdriver-createdevice">IWDFDriver::CreateDevice</a>
 

 

