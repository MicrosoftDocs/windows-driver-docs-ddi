---
UID: NF:wudfddi.IWDFDevice.AssignDeviceInterfaceState
title: IWDFDevice::AssignDeviceInterfaceState (wudfddi.h)
description: The AssignDeviceInterfaceState method enables or disables the specified device interface instance for a device.
old-location: wdf\iwdfdevice_assigndeviceinterfacestate.htm
tech.root: wdf
ms.assetid: 466af310-f2a7-4bd7-b927-df644e2e9c24
ms.date: 02/26/2018
ms.keywords: AssignDeviceInterfaceState, AssignDeviceInterfaceState method, AssignDeviceInterfaceState method,IWDFDevice interface, IWDFDevice interface,AssignDeviceInterfaceState method, IWDFDevice.AssignDeviceInterfaceState, IWDFDevice::AssignDeviceInterfaceState, UMDFDeviceObjectRef_d3c15e61-9df6-4b55-a479-375486383064.xml, umdf.iwdfdevice_assigndeviceinterfacestate, wdf.iwdfdevice_assigndeviceinterfacestate, wudfddi/IWDFDevice::AssignDeviceInterfaceState
ms.topic: method
f1_keywords:
 - "wudfddi/IWDFDevice.AssignDeviceInterfaceState"
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
- IWDFDevice.AssignDeviceInterfaceState
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFDevice::AssignDeviceInterfaceState


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>AssignDeviceInterfaceState</b> method enables or disables the specified device interface instance for a device.


## -parameters




### -param pDeviceInterfaceGuid [in]

A pointer to the GUID for a device interface class.


### -param pReferenceString [in, optional]

A pointer to a <b>NULL</b>-terminated string that contains the name of the instance of the device interface. This parameter is optional. The driver can pass <b>NULL</b> if the driver does not have to supply a name. If the driver must supply a name, the string that the driver passes must not contain any path separator characters ("/" or "\\"). 


### -param Enable [in]

A BOOL value that specifies whether the device interface instance should be enabled or disabled. <b>TRUE</b> indicates to enable; <b>FALSE</b> indicates to disable.


## -returns



<b>AssignDeviceInterfaceState</b> returns S_OK if the operation succeeds. Otherwise, this method returns one of the error codes that are defined in Winerror.h.




## -remarks



If <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice-createdeviceinterface">IWDFDevice::CreateDeviceInterface</a> succeeds, the framework automatically enables and disables the interface based on the device's PnP state.

Use the <b>AssignDeviceInterfaceState</b> method to disable and re-enable a device interface manually.



For more information about device interfaces, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-device-interfaces-in-umdf-drivers">Using Device Interfaces in UMDF Drivers</a>.


#### Examples

For a code example of how to use the <b>AssignDeviceInterfaceState</b> method, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice-createdeviceinterface">IWDFDevice::CreateDeviceInterface</a>.

<div class="code"></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfdevice">IWDFDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice-createdeviceinterface">IWDFDevice::CreateDeviceInterface</a>
 

 

