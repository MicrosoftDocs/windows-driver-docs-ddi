---
UID: NF:ntifs.FsRtlDeregisterUncProvider
title: FsRtlDeregisterUncProvider function
author: windows-driver-content
description: The FsRtlDeregisterUncProvider routine deregisters a redirector that was registered as a Universal Naming Convention (UNC) provider with the multiple UNC provider (MUP).
old-location: ifsk\fsrtlderegisteruncprovider.htm
old-project: ifsk
ms.assetid: 3f53a22f-b5d6-4e3d-987d-989bd5840b2a
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FsRtlDeregisterUncProvider, FsRtlDeregisterUncProvider routine [Installable File System Drivers], fsrtlref_d1eb1778-7643-44df-8f68-edc995b22246.xml, ifsk.fsrtlderegisteruncprovider, ntifs/FsRtlDeregisterUncProvider
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	FsRtlDeregisterUncProvider
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlDeregisterUncProvider function


## -description


The <b>FsRtlDeregisterUncProvider</b> routine deregisters a redirector that was registered as a Universal Naming Convention (UNC) provider with the multiple UNC provider (MUP).


## -syntax


````
VOID FsRtlDeregisterUncProvider(
  _In_ HANDLE Handle
);
````


## -parameters




### -param Handle [in]

MUP handle returned by <a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlregisteruncprovider~r2.md">FsRtlRegisterUncProvider</a> or <a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlregisteruncproviderex~r3.md">FsRtlRegisterUncProviderEx</a>.


## -returns



None




## -remarks



To register a UNC provider on Windows Server 2003, Windows XP, or Windows 2000, use <a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlregisteruncprovider~r2.md">FsRtlRegisterUncProvider</a>. 

To register a UNC provider on Windows Vista, use <a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlregisteruncproviderex~r3.md">FsRtlRegisterUncProviderEx</a>.

For more information, see the following sections in the Design Guide:


<a href="https://msdn.microsoft.com/07c4a498-10c7-41b2-aaeb-73cab946f392">Support for UNC Naming and MUP</a>



<a href="https://msdn.microsoft.com/8ca2f9bc-14f1-45d3-a397-f3e5459cf8ec">MUP Changes in Microsoft Windows Vista</a>





## -see-also

<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlregisteruncproviderex~r3.md">FsRtlRegisterUncProviderEx</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlregisteruncprovider~r2.md">FsRtlRegisterUncProvider</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlDeregisterUncProvider routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

