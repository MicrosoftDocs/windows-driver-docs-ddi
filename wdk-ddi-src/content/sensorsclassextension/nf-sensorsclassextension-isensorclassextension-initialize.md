---
UID: NF:sensorsclassextension.ISensorClassExtension.Initialize
title: ISensorClassExtension::Initialize (sensorsclassextension.h)
description: The ISensorClassExtension::Initialize method initializes the sensor class extension object.
old-location: sensors\isensorclassextension_initialize.htm
tech.root: sensors
ms.assetid: 9b5b9cdf-06a9-410f-87c3-b87318c25a11
ms.date: 05/03/2018
ms.keywords: ISensorClassExtension interface [Sensor Devices],Initialize method, ISensorClassExtension.Initialize, ISensorClassExtension::Initialize, Initialize, Initialize method [Sensor Devices], Initialize method [Sensor Devices],ISensorClassExtension interface, sensors.isensorclassextension_initialize, sensorsclassextension/ISensorClassExtension::Initialize
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
-	Initialize
product:
- Windows
targetos: Windows
req.typenames: 
---

# ISensorClassExtension::Initialize


## -description


The <a href="https://msdn.microsoft.com/library/windows/hardware/ff545514">ISensorClassExtension::Initialize</a> method initializes the sensor class extension object.


## -parameters




### -param pWdfDeviceUnknown

IUnknown pointer for the driver class that implements the IWDFDevice interface.


### -param pSensorDriverUnknown

IUnknown pointer for the object that implements the ISensorDriver callback interface.


## -returns



This method returns an HRESULT. Possible values include, but are not limited to, one of the following values. See Remarks.

| **Return code** | **Description** | 
|:--|:--|
| **S_OK** | The method succeeded. | 
| **E_POINTER** | The argument was NULL or the [IWDFDevice](https://msdn.microsoft.com/library/windows/hardware/ff556917) interface is missing.. | 
| **HRESULT_FROM_WIN32(ERROR_ALREADY_EXISTS)** | The class extension is already initialized. | 
| **HRESULT_FROM_WIN32(ERROR_ALREADY_INITIALIZED)** | The class extension is already initialized. | 
| **HRESULT_FROM_WIN32(ERROR_NOT_FOUND)** | The WPD_OBJECT_ID for the sensor is not valid. | 



## -remarks



First, create the sensor class extension by calling the COM CoCreateInstance method, and then call Initialize. We recommend that you perform these initialization steps when called by UMDF in <a href="https://msdn.microsoft.com/library/windows/hardware/ff556766">IPnpCallbackHardware::OnPrepareHardware</a>. After Initialize returns, the driver must be ready to receive callbacks from the sensor class extension. The sensor class extension calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff545633">ISensorDriver::OnGetSupportedSensorObjects</a> during initialization. Your driver must be ready to return values for all required properties and data fields before it calls Initialize.

Because the class extension calls your driver during initialization, this method can also return HRESULTs that your driver returns from <a href="https://msdn.microsoft.com/library/windows/hardware/ff545633">ISensorDriver::OnGetSupportedSensorObjects</a>.

<div class="code"></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545503">ISensorClassExtension</a>
 

 

