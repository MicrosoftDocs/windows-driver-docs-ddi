---
UID: NF:ntddk.MmUnsecureVirtualMemory
title: MmUnsecureVirtualMemory function
author: windows-driver-content
description: The MmUnsecureVirtualMemory routine unsecures a memory address range secured by the MmSecureVirtualMemory routine.
old-location: kernel\mmunsecurevirtualmemory.htm
old-project: kernel
ms.assetid: 979eef24-e53b-476c-b9db-e56c43630913
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ntddk/MmUnsecureVirtualMemory, MmUnsecureVirtualMemory, k106_0bfc6e9e-a4e9-4868-b1fb-da6714146dbf.xml, MmUnsecureVirtualMemory routine [Kernel-Mode Driver Architecture], kernel.mmunsecurevirtualmemory
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 2000 and later versions of Windows. This routine is not available in Windows 98/Me.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlMmApcLte, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<=APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	MmUnsecureVirtualMemory
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# MmUnsecureVirtualMemory function


## -description


The <b>MmUnsecureVirtualMemory</b> routine unsecures a memory address range secured by the <a href="..\ntddk\nf-ntddk-mmsecurevirtualmemory.md">MmSecureVirtualMemory</a> routine. 


## -syntax


````
VOID MmUnsecureVirtualMemory(
  _In_ HANDLE SecureHandle
);
````


## -parameters




### -param SecureHandle [in]

Specifies the value returned by <a href="..\ntddk\nf-ntddk-mmsecurevirtualmemory.md">MmSecureVirtualMemory</a> for the memory address range. 


## -returns



None




## -see-also

<a href="..\ntddk\nf-ntddk-mmsecurevirtualmemory.md">MmSecureVirtualMemory</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20MmUnsecureVirtualMemory routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

