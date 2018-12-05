---
UID: NF:sensorsclassextension.ISensorClassExtension.ProcessIoControl
title: ISensorClassExtension::ProcessIoControl
author: windows-driver-content
description: The ISensorClassExtension::ProcessControl method sends Windows Portable Devices (WPD) I/O control requests to the sensor class extension for processing.
old-location: sensors\isensorclassextension_processiocontrol.htm
tech.root: sensors
ms.assetid: bd886086-4e23-47c0-ae58-9234399e5a79
ms.date: 05/03/2018
ms.keywords: ISensorClassExtension interface [Sensor Devices],ProcessIoControl method, ISensorClassExtension.ProcessIoControl, ISensorClassExtension::ProcessIoControl, ProcessIoControl, ProcessIoControl method [Sensor Devices], ProcessIoControl method [Sensor Devices],ISensorClassExtension interface, sensors.isensorclassextension_processiocontrol, sensorsclassextension/ISensorClassExtension::ProcessIoControl
ms.topic: method
req.header: sensorsclassextension.h
req.include-header: 
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
req.lib: SensorsClassExtension.lib
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	SensorsClassExtension.lib
-	SensorsClassExtension.dll
api_name:
-	ProcessIoControl
product:
- Windows
targetos: Windows
req.typenames: 
---

# ISensorClassExtension::ProcessIoControl


## -description


The <a href="https://msdn.microsoft.com/bd886086-4e23-47c0-ae58-9234399e5a79">ISensorClassExtension::ProcessControl</a> method sends Windows Portable Devices (WPD) I/O control requests to the sensor class extension for processing.


## -parameters




### -param pRequest

Pointer to the IWDFIoRequest interface that represents the UMDF request object.


## -returns



This method returns an HRESULT. Possible values include, but are not limited to, one of the following values.

|Return code|Description|
|--- |--- |
|S_OK|The method succeeded.|
|E_ACCESS_DENIED|No permission. For example, the I/O request sought data for which no permission exists.|
|E_POINTER|A required pointer argument was NULL.|
|HRESULT_FROM_WIN32(ERROR_NOT_SUPPORTED)|The request did not contain a WPD IOCTL.|


## -remarks



UMDF sends I/O control requests to sensor drivers through <a href="https://msdn.microsoft.com/library/windows/hardware/ff556854">IQueueCallbackDeviceIoControl::OnDeviceIoControl</a>. We recommend that you call ProcessIoControl to forward all WPD requests to the sensor class extension for processing. You can use the WPD macro IS_WPD_IOCTL to determine whether a given control code is specific to WPD. Clients of the Sensor API and Location API send only WPD IOCTLs, which can always be process by the sensor class extension.

After processing an I/O control request, the sensor class extension uses the driver's callback interface, <a href="https://msdn.microsoft.com/library/windows/hardware/ff545566">ISensorDriver</a>, to provide notifications, as appropriate. WPD requests that the sensor class extension does not handle by default are sent to the driver through <a href="https://msdn.microsoft.com/library/windows/hardware/ff545644">ISensorDriver::OnProcessWpdMessage</a>.

The driver must not complete I/O control requests that it forwards to the sensor class extension.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545503">ISensorClassExtension</a>
 

 

