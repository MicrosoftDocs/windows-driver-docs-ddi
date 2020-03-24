---
UID: NF:sensorsclassextension.ISensorClassExtension.CleanupFile
title: ISensorClassExtension::CleanupFile (sensorsclassextension.h)
description: The ISensorClassExtension::CleanupFile method notifies the class extension about a file handle that closes and cancels all pending I/O requests, for the specified application.
old-location: sensors\isensorclassextension_cleanupfile.htm
tech.root: sensors
ms.assetid: eeade123-fb83-478f-99e3-e79bbbb1919b
ms.date: 05/03/2018
keywords: ["ISensorClassExtension::CleanupFile"]
ms.keywords: CleanupFile, CleanupFile method [Sensor Devices], CleanupFile method [Sensor Devices],ISensorClassExtension interface, ISensorClassExtension interface [Sensor Devices],CleanupFile method, ISensorClassExtension.CleanupFile, ISensorClassExtension::CleanupFile, sensors.isensorclassextension_cleanupfile, sensorsclassextension/ISensorClassExtension::CleanupFile
f1_keywords:
 - "sensorsclassextension/CleanupFile"
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- SensorsClassExtension.lib
- SensorsClassExtension.dll
api_name:
- CleanupFile
product:
- Windows
targetos: Windows
req.typenames: 
---

# ISensorClassExtension::CleanupFile


## -description


The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sensorsclassextension/nf-sensorsclassextension-isensorclassextension-cleanupfile">ISensorClassExtension::CleanupFile</a> method notifies the class extension about a file handle that closes and cancels all pending I/O requests, for the specified application.


## -parameters




### -param pWdfFile

Pointer to an IWDFFile interface that represents the file object for the application being closed.


## -returns



This method returns an HRESULT. Possible values include, but are not limited to, one of the following values.

|Return code|Description|
|--- |--- |
|S_OK|The method succeeded.|
|E_POINTER|A required pointer argument was NULL.|
|HRESULT_FROM_WIN32(ERROR_CAN_NOT_COMPLETE)|The class extension is not initialized.|


## -remarks



Your driver must call this method to forward <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-ifilecallbackcleanup-oncleanupfile">IFileCallbackCleanup::OnCleanupFile</a> method calls from UMDF. You receive this call any time that a file handle closes. Typically, you receive this call after an application stops responding.

When finished, the sensor class extension calls the driver in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sensorsclassextension/nf-sensorsclassextension-isensordriver-onclientdisconnect">ISensorDriver::OnClientDisconnect</a>, and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sensorsclassextension/nf-sensorsclassextension-isensordriver-onclientunsubscribefromevents">ISensorDriver::OnClientUnsubscribeFromEvents</a>, if applicable.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sensorsclassextension/nn-sensorsclassextension-isensorclassextension">ISensorClassExtension</a>
 

 

