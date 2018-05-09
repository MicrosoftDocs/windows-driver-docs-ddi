---
UID: NF:sensorsclassextension.ISensorClassExtension.CleanupFile
title: ISensorClassExtension::CleanupFile
author: windows-driver-content
description: The ISensorClassExtension::CleanupFile method notifies the class extension about a file handle that closes and cancels all pending I/O requests, for the specified application.
old-location: sensors\isensorclassextension_cleanupfile.htm
old-project: sensors
ms.assetid: eeade123-fb83-478f-99e3-e79bbbb1919b
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: CleanupFile, CleanupFile method [Sensor Devices], CleanupFile method [Sensor Devices],ISensorClassExtension interface, ISensorClassExtension interface [Sensor Devices],CleanupFile method, ISensorClassExtension.CleanupFile, ISensorClassExtension::CleanupFile, sensors.isensorclassextension_cleanupfile, sensorsclassextension/ISensorClassExtension::CleanupFile
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
-	CleanupFile
product:
- Windows
targetos: Windows
req.typenames: 
---

# ISensorClassExtension::CleanupFile


## -description


The <a href="https://msdn.microsoft.com/library/windows/hardware/ff545512">ISensorClassExtension::CleanupFile</a> method notifies the class extension about a file handle that closes and cancels all pending I/O requests, for the specified application.


## -parameters




### -param pWdfFile

Pointer to an IWDFFile interface that represents the file object for the application being closed.


## -returns



This method returns an HRESULT. Possible values include, but are not limited to, one of the following values.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The method succeeded.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_POINTER</b></dt>
</dl>
</td>
<td width="60%">
A required pointer argument was <b>NULL</b>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HRESULT_FROM_WIN32(ERROR_CAN_NOT_COMPLETE)</b></dt>
</dl>
</td>
<td width="60%">
The class extension is not initialized.

</td>
</tr>
</table>
 




## -remarks



Your driver must call this method to forward <a href="https://msdn.microsoft.com/library/windows/hardware/ff554905">IFileCallbackCleanup::OnCleanupFile</a> method calls from UMDF. You receive this call any time that a file handle closes. Typically, you receive this call after an application stops responding.

When finished, the sensor class extension calls the driver in <a href="https://msdn.microsoft.com/9484610b-4cbd-4c4e-9e60-ef052702325c">ISensorDriver::OnClientDisconnect</a>, and <a href="https://msdn.microsoft.com/library/windows/hardware/ff545598">ISensorDriver::OnClientUnsubscribeFromEvents</a>, if applicable.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545503">ISensorClassExtension</a>
 

 

