---
UID: NF:ntifs.IoVerifyVolume
title: IoVerifyVolume function (ntifs.h)
description: The IoVerifyVolume routine sends a volume verify request to the given removable-media device.
old-location: ifsk\ioverifyvolume.htm
tech.root: ifsk
ms.assetid: 46e29607-ee09-4db4-a501-68a3bc678e16
ms.date: 04/16/2018
ms.keywords: IoVerifyVolume, IoVerifyVolume routine [Installable File System Drivers], ifsk.ioverifyvolume, ioref_b55e7a87-a18d-4ccd-ab32-061676c9dde4.xml, ntifs/IoVerifyVolume
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "< DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	IoVerifyVolume
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoVerifyVolume function


## -description


The <b>IoVerifyVolume</b> routine sends a volume verify request to the given removable-media device. 


## -parameters




### -param DeviceObject [in]

Pointer to the device object for the device on which the volume is to be verified. 


### -param AllowRawMount [in]

Set to <b>TRUE</b> if this verify request is being issued on behalf of a DASD open request and a raw mount should be performed if the verify request fails.


## -returns



<b>IoVerifyVolume</b> can return one of the following NTSTATUS values: 

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
<td width="60%"></td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%"></td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>
</td>
<td width="60%"></td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_WRONG_VOLUME</b></dt>
</dl>
</td>
<td width="60%"></td>
</tr>
</table>
 




## -remarks



<b>IoVerifyVolume</b> sends a volume verify request to the given removable-media device. 

If the verify operation fails, the I/O Manager sends a volume mount request to the device. 

Before using <a href="https://msdn.microsoft.com/library/windows/hardware/ff548529">IoSetDeviceToVerify</a> and <b>IoVerifyVolume</b>, driver writers are strongly encouraged to study the way these routines are used in the FASTFAT sample. 

For more information about removable-media devices, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563916">Supporting Removable Media</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff549212">IoGetDeviceToVerify</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548529">IoSetDeviceToVerify</a>
 

 

