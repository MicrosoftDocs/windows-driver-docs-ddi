---
UID: NF:sensorsclassextension.ISensorDriver.OnProcessWpdMessage
title: ISensorDriver::OnProcessWpdMessage method
author: windows-driver-content
description: The ISensorDriver::OnProcessWpdMessage method handles Windows Portable Device (WPD) commands that the ISensorClassExtension::ProcessIoControl method does not handle internally.
old-location: sensors\isensordriver_onprocesswpdmessage.htm
old-project: sensors
ms.assetid: 4780d0ea-a54a-4125-b3b6-2210a14eff71
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: ISensorDriver, ISensorDriver::OnProcessWpdMessage, OnProcessWpdMessage
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: sensorsclassextension.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: OnProcessWpdMessage
req.alt-loc: SensorsClassExtension.lib,SensorsClassExtension.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: SensorsClassExtension.lib
req.dll: 
req.irql: 
req.typenames: SensorConnectionType
req.product: Windows 10 or later.
---

# ISensorDriver::OnProcessWpdMessage method



## -description
The <a href="https://msdn.microsoft.com/library/windows/hardware/ff545644">ISensorDriver::OnProcessWpdMessage</a> method handles Windows Portable Device (WPD) commands that the <a href="https://msdn.microsoft.com/library/windows/hardware/ff545536">ISensorClassExtension::ProcessIoControl</a> method does not handle internally. 



## -syntax

````
HRESULT OnProcessWpdMessage(
   IUnknown * pUnkPortableDeviceValuesParams,
   IUnknown * pUnkPortableDeviceValuesResults
);
````


## -parameters

### -param pUnkPortableDeviceValuesParams 

A pointer to the IUnknown interface that supports the IPortableDeviceValues interface. The object that is associated with this IUnknown interface contains the parameters for the WPD command. For more information, see IPortableDeviceValues in Windows Portable Devices. 


### -param pUnkPortableDeviceValuesResults 

A pointer to the IUnknown interface that supports the IPortableDeviceValues interface. The object that is associated with this IUnknown interface stores the results for the WPD command. 


## -returns
If the operation succeeds, this method returns S_OK. Otherwise, this method returns one of the error codes that are defined in Winerror.h.


## -remarks
This method enables you to extend the WPD commands and interfaces in a device-specific way.</p>