---
UID: NF:wudfddi.IPnpCallback.OnD0Entry
title: IPnpCallback::OnD0Entry (wudfddi.h)
description: The OnD0Entry method notifies a driver when a device enters the D0 power state so that the driver can perform necessary operations, such as enabling the device.
old-location: wdf\ipnpcallback_ond0entry.htm
tech.root: wdf
ms.assetid: 6efa3d8e-3e54-4ab1-82e0-08ba12bb1877
ms.date: 02/26/2018
ms.keywords: IPnpCallback interface,OnD0Entry method, IPnpCallback.OnD0Entry, IPnpCallback::OnD0Entry, OnD0Entry, OnD0Entry method, OnD0Entry method,IPnpCallback interface, UMDFDeviceObjectRef_96da33eb-c6ef-41f0-9a4c-1a8e8158d023.xml, umdf.ipnpcallback_ond0entry, wdf.ipnpcallback_ond0entry, wudfddi/IPnpCallback::OnD0Entry
ms.topic: method
f1_keywords:
 - "wudfddi/IPnpCallback.OnD0Entry"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- Wudfddi.h
api_name:
- IPnpCallback.OnD0Entry
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPnpCallback::OnD0Entry


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>OnD0Entry</b> method notifies a driver when a device enters the D0 power state so that the driver can perform necessary operations, such as enabling the device. 


## -parameters




### -param pWdfDevice [in]

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfdevice">IWDFDevice</a> interface for the device object of the device that enters the D0 power state.


### -param previousState [in]

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ne-wdfdevice-_wdf_power_device_state">WDF_POWER_DEVICE_STATE</a>-typed value that identifies the power state of the device before it entered the D0 power state.


## -returns



If the <b>OnD0Entry</b> callback encounters no errors, it must return
       S_OK or another status code for which SUCCEEDED(status) equals <b>TRUE</b>.

 If it returns a status code for which SUCCEEDED(status) equals <b>FALSE</b>, the framework removes the device. If the device's drivers are not supporting other devices on the system, the I/O manager unloads the drivers. 
The framework notifies the PnP manager, which then attempts to restart the device by requesting the bus driver to reenumerate its devices. If your driver was unloaded, it will be reloaded.    In this case, the framework will not call the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-ipnpcallback-ond0exit">IPnpCallback::OnD0Exit</a> callback function.

HRESULT error codes are defined in Winerror.h. 




## -remarks



A driver registers the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-ipnpcallback">IPnpCallback</a> interface when it calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdriver-createdevice">IWDFDriver::CreateDevice</a> method to create a device object. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-ipnpcallback">IPnpCallback</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfdevice">IWDFDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdriver-createdevice">IWDFDriver::CreateDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ne-wdfdevice-_wdf_power_device_state">WDF_POWER_DEVICE_STATE</a>
 

 

