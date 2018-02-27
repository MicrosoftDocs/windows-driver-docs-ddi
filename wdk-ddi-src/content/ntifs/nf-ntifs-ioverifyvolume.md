---
UID: NF:ntifs.IoVerifyVolume
title: IoVerifyVolume function
author: windows-driver-content
description: The IoVerifyVolume routine sends a volume verify request to the given removable-media device.
old-location: ifsk\ioverifyvolume.htm
old-project: ifsk
ms.assetid: 46e29607-ee09-4db4-a501-68a3bc678e16
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: IoVerifyVolume, IoVerifyVolume routine [Installable File System Drivers], ifsk.ioverifyvolume, ioref_b55e7a87-a18d-4ccd-ab32-061676c9dde4.xml, ntifs/IoVerifyVolume
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	IoVerifyVolume
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# IoVerifyVolume function


## -description


The <b>IoVerifyVolume</b> routine sends a volume verify request to the given removable-media device. 


## -syntax


````
NTSTATUS IoVerifyVolume(
  _In_ PDEVICE_OBJECT DeviceObject,
  _In_ BOOLEAN        AllowRawMount
);
````


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

Before using <a href="..\ntifs\nf-ntifs-iosetdevicetoverify.md">IoSetDeviceToVerify</a> and <b>IoVerifyVolume</b>, driver writers are strongly encouraged to study the way these routines are used in the FASTFAT sample. 

For more information about removable-media devices, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563916">Supporting Removable Media</a>. 




## -see-also

<a href="..\ntifs\nf-ntifs-iogetdevicetoverify.md">IoGetDeviceToVerify</a>



<a href="..\ntifs\nf-ntifs-iosetdevicetoverify.md">IoSetDeviceToVerify</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20IoVerifyVolume routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

