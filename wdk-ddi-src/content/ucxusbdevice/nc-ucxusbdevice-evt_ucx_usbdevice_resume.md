---
UID: NC:ucxusbdevice.EVT_UCX_USBDEVICE_RESUME
title: EVT_UCX_USBDEVICE_RESUME (ucxusbdevice.h)
description: UCX invokes this callback function to resume a device from suspend state.
old-location: buses\evt_ucx_usbdevice_resume.htm
tech.root: usbref
ms.assetid: 876D9754-B3AA-42C5-8BDD-60CFD4F78951
ms.date: 05/07/2018
ms.keywords: "*PFN_UCX_USBDEVICE_RESUME, *PFN_UCX_USBDEVICE_RESUME callback function [Buses], EVT_UCX_USBDEVICE_RESUME, EVT_UCX_USBDEVICE_RESUME callback, EvtUcxDeviceResume, EvtUcxDeviceResume callback function [Buses], buses.evt_ucx_usbdevice_resume, ucxusbdevice/EvtUcxDeviceResume"
ms.topic: callback
req.header: ucxusbdevice.h
req.include-header: Ucxclass.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- ucxusbdevice.h
api_name:
- *PFN_UCX_USBDEVICE_RESUME
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_UCX_USBDEVICE_RESUME callback function


## -description


UCX invokes this callback function to resume a device from suspend state.


## -parameters




### -param UcxController [in]

 A handle to the UCX controller that the client driver received in a previous call to  the <a href="https://msdn.microsoft.com/library/windows/hardware/mt188033">UcxControllerCreate</a> method.


### -param UcxUsbDevice [in]

A handle to a UCX object that represents the USB device that the client driver received in a previous call to the <a href="https://msdn.microsoft.com/library/windows/hardware/mt188052">UcxUsbDeviceCreate</a> method.


## -returns



This callback function does not return a value.




## -remarks



The UCX client driver registers its implementation with the USB host controller extension (UCX) by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/mt188052">UcxUsbDeviceCreate</a> method.



