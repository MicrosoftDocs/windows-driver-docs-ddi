---
UID: NF:wdm.KdChangeOption
title: KdChangeOption function
description: The KdChangeOption routine accesses and changes state in the kernel that is related to kernel debugging.
old-location: devtest\kdchangeoption.htm
tech.root: devtest
ms.assetid: 6f93b62b-6dc2-417b-9e1c-44be628c489c
ms.date: 02/23/2018
ms.keywords: DebugFns_7d909b99-2ffb-4c60-9738-cb35c9a0c4fa.xml, KdChangeOption, KdChangeOption routine [Driver Development Tools], devtest.kdchangeoption, wdm/KdChangeOption
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows Server 2003 with Service Pack 1 (SP1) and later versions of Windows and Windows Server.
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
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	KdChangeOption
product:
- Windows
targetos: Windows
req.typenames: 
---

# KdChangeOption function


## -description


The <b>KdChangeOption</b> routine accesses and changes state in the kernel that is related to kernel debugging. 


## -parameters




### -param Option [in]

A value from the KD_OPTION enumeration that indicates the kernel state to access and change. The value of this parameter determines the format and required length of the <i>InBuffer</i> and <i>OutBuffer</i>. Currently, the only valid value is KD_OPTION_SET_BLOCK_ENABLE. 


### -param OPTIONAL [in, optional]

The size, in bytes, of the buffer at <i>InBuffer</i>. This value is optional. 


### -param InBuffer [in]

A pointer to a caller-allocated input buffer that contains information about the kernel state to change. If <i>Option</i> specifies a kernel state that does not require input data, this pointer can be <b>NULL</b>.

### -param OPTIONAL [in, optional]

The size, in bytes, of the buffer at <i>OutBuffer</i>. This value is optional.

### -param OutBuffer [out]

A pointer to a caller-allocated output buffer in which information that pertains to the kernel state is returned. If <i>Option</i> specifies a kernel state that does not produce output data, this pointer can be <b>NULL</b>. 

### -param OPTIONAL [out, optional]

A pointer to a variable that receives the size, in bytes, of the required output buffer at <i>OutBuffer</i>. This value is optional.


## -returns



<b>KdChangeOption</b> returns STATUS_SUCCESS if it successfully carried out the requested operation. Otherwise, the return value can be one of the following error status codes: 

STATUS_ACCESS_DENIED

STATUS_INVALID_INFO_CLASS

STATUS_INVALID_PARAMETER

STATUS_DEBUGGER_INACTIVE




## -remarks



If the operating system was booted with no debug controls, <b>KdChangeOption</b> returns STATUS_DEBUGGER_INACTIVE.

Currently, the only valid value for the <i>Option</i> parameter is KD_OPTION_SET_BLOCK_ENABLE. If <i>Option</i> is set to any other value, <b>KdChangeOption</b> returns STATUS_INVALID_INFO_CLASS. When <i>Option</i> is KD_OPTION_SET_BLOCK_ENABLE, the caller must set the <i>InBufferBytes</i> parameter to <b>sizeof</b>(BOOLEAN), the <i>OutBufferBytes</i> parameter to zero, and the <i>OutBuffer</i> parameter to <b>NULL</b>; otherwise, <b>KdChangeOption</b> returns STATUS_INVALID_PARAMETER. If the high bit (0x80) in the <b>KdBlockEnable</b> system variable is set to one, the debugger can never be re-enabled, and <b>KdChangeOption</b> returns STATUS_ACCESS_DENIED. Otherwise, <b>KdChangeOption</b> sets the <b>KdBlockEnable</b> system variable to the BOOLEAN value that <i>InBuffer</i> points to.



