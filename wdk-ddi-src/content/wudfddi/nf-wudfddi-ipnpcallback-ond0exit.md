---
UID: NF:wudfddi.IPnpCallback.OnD0Exit
title: IPnpCallback::OnD0Exit (wudfddi.h)
description: The OnD0Exit method notifies a driver when a device exits the D0 power state so that the driver can perform necessary operations, such as disabling the device.
old-location: wdf\ipnpcallback_ond0exit.htm
tech.root: wdf
ms.assetid: 39eedeca-269d-4966-be1f-7cc5c9228a5c
ms.date: 02/26/2018
keywords: ["IPnpCallback::OnD0Exit"]
ms.keywords: IPnpCallback interface,OnD0Exit method, IPnpCallback.OnD0Exit, IPnpCallback::OnD0Exit, OnD0Exit, OnD0Exit method, OnD0Exit method,IPnpCallback interface, UMDFDeviceObjectRef_4c9ce2f7-92c8-4e0b-80fe-cfb06d1be83a.xml, umdf.ipnpcallback_ond0exit, wdf.ipnpcallback_ond0exit, wudfddi/IPnpCallback::OnD0Exit
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - IPnpCallback::OnD0Exit
 - wudfddi/IPnpCallback::OnD0Exit
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Wudfddi.h
api_name:
 - IPnpCallback.OnD0Exit
---

# IPnpCallback::OnD0Exit


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>OnD0Exit</b> method notifies a driver when a device exits the D0 power state so that the driver can perform necessary operations,  such as disabling the device.

## -parameters

### -param pWdfDevice 

[in]
A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfdevice">IWDFDevice</a> interface for the device object of the device that exits the D0 power state.

### -param newState 

[in]
A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ne-wdfdevice-_wdf_power_device_state">WDF_POWER_DEVICE_STATE</a>-typed value that identifies the new power state that the device is set to after it exits the D0 power state.

## -returns

If the 
      <b>OnD0Exit</b> callback method encounters no errors, it must return S_OK or another status code for which SUCCEEDED(status) equals <b>TRUE</b>. Otherwise, it must return a status code for which SUCCEEDED(status) equals <b>FALSE</b>.   HRESULT error codes are defined in Winerror.h.

## -remarks

A driver registers the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-ipnpcallback">IPnpCallback</a> interface when it calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdriver-createdevice">IWDFDriver::CreateDevice</a> method to create a device object.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-ipnpcallback">IPnpCallback</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfdevice">IWDFDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdriver-createdevice">IWDFDriver::CreateDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ne-wdfdevice-_wdf_power_device_state">WDF_POWER_DEVICE_STATE</a>

