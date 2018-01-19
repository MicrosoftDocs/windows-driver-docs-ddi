---
UID: NF:sensorsclassextension.ISensorClassExtension.CleanupFile
title: ISensorClassExtension::CleanupFile method
author: windows-driver-content
description: The ISensorClassExtension::CleanupFile method notifies the class extension about a file handle that closes and cancels all pending I/O requests, for the specified application.
old-location: sensors\isensorclassextension_cleanupfile.htm
old-project: sensors
ms.assetid: eeade123-fb83-478f-99e3-e79bbbb1919b
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: ISensorClassExtension, ISensorClassExtension::CleanupFile, CleanupFile
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
req.alt-api: CleanupFile
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

# ISensorClassExtension::CleanupFile method



## -description
The <a href="https://msdn.microsoft.com/library/windows/hardware/ff545512">ISensorClassExtension::CleanupFile</a> method notifies the class extension about a file handle that closes and cancels all pending I/O requests, for the specified application.



## -syntax

````
HRESULT CleanupFile(
   IWDFFile * pWdfFile
);
````


## -parameters

### -param pWdfFile 

Pointer to an IWDFFile interface that represents the file object for the application being closed.


## -returns
This method returns an HRESULT. Possible values include, but are not limited to, one of the following values.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method succeeded.
<dl>
<dt><b>E_POINTER</b></dt>
</dl>A required pointer argument was <b>NULL</b>.
<dl>
<dt><b>HRESULT_FROM_WIN32(ERROR_CAN_NOT_COMPLETE)</b></dt>
</dl>The class extension is not initialized.

 


## -remarks
Your driver must call this method to forward <a href="https://msdn.microsoft.com/library/windows/hardware/ff554905">IFileCallbackCleanup::OnCleanupFile</a> method calls from UMDF. You receive this call any time that a file handle closes. Typically, you receive this call after an application stops responding.

When finished, the sensor class extension calls the driver in <a href="https://msdn.microsoft.com/9484610b-4cbd-4c4e-9e60-ef052702325c">ISensorDriver::OnClientDisconnect</a>, and <a href="https://msdn.microsoft.com/library/windows/hardware/ff545598">ISensorDriver::OnClientUnsubscribeFromEvents</a>, if applicable.</p>