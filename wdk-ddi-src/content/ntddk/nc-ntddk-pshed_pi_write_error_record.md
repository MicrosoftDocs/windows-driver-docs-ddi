---
UID: NC:ntddk.PSHED_PI_WRITE_ERROR_RECORD
title: PSHED_PI_WRITE_ERROR_RECORD
author: windows-driver-content
description: A PSHED plug-in's WriteErrorRecord callback function writes an error record to the system's persistent data storage.
old-location: whea\writeerrorrecord.htm
tech.root: whea
ms.assetid: 4800a0f9-29ee-4631-aee8-5a4924a08f55
ms.date: 2/20/2018
ms.keywords: PSHED_PI_WRITE_ERROR_RECORD, PSHED_PI_WRITE_ERROR_RECORD callback, WriteErrorRecord, WriteErrorRecord callback function [WHEA Drivers and Applications], ntddk/WriteErrorRecord, whea.writeerrorrecord, whearef_3a405d7d-3427-4c22-919e-7cbab5ea4f19.xml
ms.topic: callback
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows.
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
req.irql: "<= HIGH_LEVEL (See Remarks section)"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Ntddk.h
api_name:
-	WriteErrorRecord
product:
- Windows
targetos: Windows
req.typenames: 
---

# PSHED_PI_WRITE_ERROR_RECORD callback function


## -description


A PSHED plug-in's <i>WriteErrorRecord </i>callback function writes an error record to the system's persistent data storage.


## -parameters




### -param PluginContext [in, out, optional]

A pointer to the context area that was specified in the <b>Context</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560617">WHEA_PSHED_PLUGIN_REGISTRATION_PACKET</a> structure when the PSHED plug-in called the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559466">PshedRegisterPlugin</a> function to register itself with the PSHED.


### -param Flags [in]

A bit-wise OR'ed combination of flags that affect the write operation. A possible flag is:





#### WHEA_WRITE_FLAG_DUMMY

The write operation is a dummy write operation. No data is to be written to the system's persistent data storage.


### -param RecordLength [in]

The size, in bytes, of the error record pointed to by the <i>ErrorRecord</i> parameter.


### -param ErrorRecord [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff560483">WHEA_ERROR_RECORD</a> structure that describes the error record that is being written to the system's persistent data storage.


## -returns



A PSHED plug-in's <i>WriteErrorRecord</i> callback function returns one of the following NTSTATUS codes:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The error record was successfully written to the system's persistent data storage.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>
</td>
<td width="60%">
An error occurred.

</td>
</tr>
</table>
 




## -remarks



A PSHED plug-in that participates in error record persistence sets the <b>Callbacks.WriteErrorRecord</b>, <b>Callbacks.ReadErrorRecord </b>and <b>Callbacks.ClearErrorRecord </b>members of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560617">WHEA_PSHED_PLUGIN_REGISTRATION_PACKET</a> structure to point to its <i>WriteErrorRecord</i>, <a href="https://msdn.microsoft.com/2fcbdfe3-bcce-4e5b-a16b-501612975e82">ReadErrorRecord</a>, and <a href="https://msdn.microsoft.com/e9893f9c-7fbd-4a02-8c2d-d7c480ed5198">ClearErrorRecord</a> callback functions when the plug-in calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559466">PshedRegisterPlugin</a> function to register itself with the PSHED. The PSHED plug-in must also set the <b>PshedFAErrorRecordPersistence</b> flag in the <b>FunctionalAreaMask</b> member of the WHEA_PSHED_PLUGIN_REGISTRATION_PACKET structure.

The Windows kernel calls into the PSHED to write an error record to the system's persistent data storage whenever a fatal or otherwise unrecoverable error condition exists so that the error record is preserved while the system is restarted. If a PSHED plug-in is registered to participate in error record persistence, the PSHED calls the PSHED plug-in's <i>WriteErrorRecord</i> callback function to perform the write operation. The mechanism that is used to write the error record to the system's persistent data storage is platform-specific.

The PSHED calls a PSHED plug-in's <i>WriteErrorRecord</i> callback function at IRQL &lt;= HIGH_LEVEL. The exact IRQL at which this callback function is called depends on the specific type of hardware error that occurred.




## -see-also




<a href="https://msdn.microsoft.com/e9893f9c-7fbd-4a02-8c2d-d7c480ed5198">ClearErrorRecord</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559466">PshedRegisterPlugin</a>



<a href="https://msdn.microsoft.com/2fcbdfe3-bcce-4e5b-a16b-501612975e82">ReadErrorRecord</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560483">WHEA_ERROR_RECORD</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560617">WHEA_PSHED_PLUGIN_REGISTRATION_PACKET</a>
 

 

