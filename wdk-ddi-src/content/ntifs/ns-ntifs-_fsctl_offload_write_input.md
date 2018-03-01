---
UID: NS:ntifs._FSCTL_OFFLOAD_WRITE_INPUT
title: "_FSCTL_OFFLOAD_WRITE_INPUT"
author: windows-driver-content
description: The FSCTL_OFFLOAD_WRITE_INPUT structure contains the input for the FSCTL_OFFLOAD_WRITE control code request.
old-location: ifsk\fsctl_offload_write_input.htm
old-project: ifsk
ms.assetid: 4ADBBBDC-02DD-4D1A-B697-6286D7513B2E
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PFSCTL_OFFLOAD_WRITE_INPUT, FSCTL_OFFLOAD_WRITE_INPUT, FSCTL_OFFLOAD_WRITE_INPUT structure [Installable File System Drivers], PFSCTL_OFFLOAD_WRITE_INPUT, PFSCTL_OFFLOAD_WRITE_INPUT structure pointer [Installable File System Drivers], _FSCTL_OFFLOAD_WRITE_INPUT, ifsk.fsctl_offload_write_input, ntifs/FSCTL_OFFLOAD_WRITE_INPUT, ntifs/PFSCTL_OFFLOAD_WRITE_INPUT"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntifs.h
req.include-header: Ntifs.h, Fltkernel.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8.
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntifs.h
api_name:
-	FSCTL_OFFLOAD_WRITE_INPUT
product: Windows
targetos: Windows
req.typenames: FSCTL_OFFLOAD_WRITE_INPUT, *PFSCTL_OFFLOAD_WRITE_INPUT
---

# _FSCTL_OFFLOAD_WRITE_INPUT structure


## -description


The <b>FSCTL_OFFLOAD_WRITE_INPUT</b> structure contains the input for the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451122">FSCTL_OFFLOAD_WRITE</a> control code request.


## -syntax


````
typedef struct _FSCTL_OFFLOAD_WRITE_INPUT {
  ULONG     Size;
  ULONG     Flags;
  ULONGLONG FileOffset;
  ULONGLONG CopyLength;
  ULONGLONG TransferOffset;
  UCHAR     Token[512];
} FSCTL_OFFLOAD_WRITE_INPUT, *PFSCTL_OFFLOAD_WRITE_INPUT;
````


## -struct-fields




### -field Size

The size of this structure. Set this member to <b>sizeof</b>(FSCTL_OFFLOAD_WRITE_INPUT).


### -field Flags

 This member is not used. Set to 0.


### -field FileOffset

 The position in the file to begin writing to. The offset value must be aligned to a logical sector boundary on the volume.


### -field CopyLength

 The length, in bytes, of data to write, starting at <b>FileOffset</b>. The length  value must align to a logical sector boundary on the volume, except when the length matches end-of-file.


### -field TransferOffset

 The position in the data associated with <b>Token</b> to begin writing from.


### -field Token

A byte array that contains a token structure, <a href="..\ntddstor\ns-ntddstor-_storage_offload_token.md">STORAGE_OFFLOAD_TOKEN</a>, representing a file data range to be logically written. The contents of <b>Token</b>  must remain unmodified between offload operations.


## -remarks



<b>CopyLength</b> can be zero. The value of <b>FileOffset</b> + <b>CopyLength</b> is bounded by both <b>MAXULONGLONG</b> and <b>MAXFILESIZE</b>. <a href="https://msdn.microsoft.com/library/windows/hardware/hh451122">FSCTL_OFFLOAD_WRITE</a> will return with <b>STATUS_INVALID_PARAMETER</b> if these conditions are not met.




## -see-also

<a href="..\ntifs\ns-ntifs-_fsctl_offload_write_output.md">FSCTL_OFFLOAD_WRITE_OUTPUT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451122">FSCTL_OFFLOAD_WRITE</a>



<a href="..\ntddstor\ns-ntddstor-_storage_offload_token.md">STORAGE_OFFLOAD_TOKEN</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451101">FSCTL_OFFLOAD_READ</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FSCTL_OFFLOAD_WRITE_INPUT structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

