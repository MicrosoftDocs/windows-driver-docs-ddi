---
UID: NF:spb.SPB_TRANSFER_LIST_ENTRY_INIT_MDL
title: SPB_TRANSFER_LIST_ENTRY_INIT_MDL function
author: windows-driver-content
description: The SPB_TRANSFER_LIST_ENTRY_INIT_MDL function returns an SPB_TRANSFER_LIST_ENTRY structure that is initialized to use an MDL to describe a data buffer.
old-location: spb\spb_transfer_list_entry_init_mdl.htm
old-project: SPB
ms.assetid: FFE8761B-5769-48E5-ACE9-50009C490714
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: SPB_TRANSFER_LIST_ENTRY_INIT_MDL function [Buses], SPB.spb_transfer_list_entry_init_mdl, spb/SPB_TRANSFER_LIST_ENTRY_INIT_MDL, SPB_TRANSFER_LIST_ENTRY_INIT_MDL
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: spb.h
req.include-header: 
req.target-type: Desktop
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: Any IRQL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Spb.h
apiname:
-	SPB_TRANSFER_LIST_ENTRY_INIT_MDL
product: Windows
targetos: Windows
req.typenames: "*PSPB_TRANSFER_DIRECTION, SPB_TRANSFER_DIRECTION"
req.product: Windows 10 or later.
---

# SPB_TRANSFER_LIST_ENTRY_INIT_MDL function


## -description


The <b>SPB_TRANSFER_LIST_ENTRY_INIT_MDL</b> function returns an <a href="https://msdn.microsoft.com/library/windows/hardware/hh406223">SPB_TRANSFER_LIST_ENTRY</a> structure that is initialized to use an MDL to describe a data buffer.


## -syntax


````
SPB_TRANSFER_LIST_ENTRY SPB_TRANSFER_LIST_ENTRY_INIT_MDL(
  _In_ SPB_TRANSFER_DIRECTION Direction,
  _In_ ULONG                  DelayInUs,
  _In_ PMDL                   Mdl
);
````


## -parameters




### -param Direction [in]

The direction of the transfer. The function writes this value to the <b>Direction</b> member of the <b>SPB_TRANSFER_LIST_ENTRY</b> structure.


### -param DelayInUs [in]

An optional delay in microseconds. The function writes this value to the <b>DelayInUs</b> member of the <b>SPB_TRANSFER_LIST_ENTRY</b> structure.


### -param Mdl [in]

A pointer to an MDL that describes a data buffer. The function writes this value to the <b>Buffer.Mdl</b> member of the <b>SPB_TRANSFER_LIST_ENTRY</b> structure. For more information, see the description of the <b>Mdl</b> member in <a href="https://msdn.microsoft.com/library/windows/hardware/hh406215">SPB_TRANSFER_BUFFER</a>.


## -returns



<b>SPB_TRANSFER_LIST_ENTRY_INIT_MDL</b> returns an initialized <b>SPB_TRANSFER_LIST_ENTRY</b> structure.




## -remarks



This initialization function returns an unnamed local variable of type <b>SPB_TRANSFER_LIST_ENTRY</b>. The storage for this variable is allocated in the caller's stack frame and is valid while the stack frame remains in scope.

<b>SPB_TRANSFER_LIST_ENTRY_INIT_MDL</b> sets the <b>Buffer.Format</b> member of the  <b>SPB_TRANSFER_LIST_ENTRY</b> structure to <b>SpbTransferBufferFormatMdl</b>. For more information about buffer formats, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh406216">SPB_TRANSFER_BUFFER_FORMAT</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh406215">SPB_TRANSFER_BUFFER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406223">SPB_TRANSFER_LIST_ENTRY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406216">SPB_TRANSFER_BUFFER_FORMAT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [SPB\buses]:%20SPB_TRANSFER_LIST_ENTRY_INIT_MDL function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

