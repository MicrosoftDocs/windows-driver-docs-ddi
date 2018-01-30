---
UID: NF:ntddk.RtlNumberGenericTableElementsAvl
title: RtlNumberGenericTableElementsAvl function
author: windows-driver-content
description: The RtlNumberGenericTableElementsAvl routine returns the number of elements in a generic table.
old-location: ifsk\rtlnumbergenerictableelementsavl.htm
old-project: ifsk
ms.assetid: CC67993A-99B1-41DC-9278-7A475EF87089
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: RtlNumberGenericTableElementsAvl, ntddk/RtlNumberGenericTableElementsAvl, RtlNumberGenericTableElementsAvl routine [Installable File System Drivers], ifsk.rtlnumbergenerictableelementsavl
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows XP.
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
req.irql: "< DISPATCH_LEVEL (see Remarks section)"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	RtlNumberGenericTableElementsAvl
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# RtlNumberGenericTableElementsAvl function


## -description


The <b>RtlNumberGenericTableElementsAvl</b> routine returns the number of elements in a generic table. 


## -syntax


````
ULONG RtlNumberGenericTableElementsAvl(
  _In_ PRTL_AVL_TABLE Table
);
````


## -parameters




### -param Table [in]

Pointer to the generic table (<a href="..\ntddk\ns-ntddk-_rtl_avl_table.md">RTL_AVL_TABLE</a>). The table must have been initialized by calling <a href="..\ntddk\nf-ntddk-rtlinitializegenerictableavl.md">RtlInitializeGenericTableAvl</a>.


## -returns


<b>RtlNumberGenericTableElementsAvl</b> returns the number of elements that are currently stored in the table. 



## -remarks


By default, the operating system uses splay trees to implement generic tables, but the <b>RtlNumberGenericTableElementsAvl</b> routine only works with Adelson-Velsky/Landis (AVL) trees. To configure the generic table routines to use AVL trees instead of splay trees in your driver, insert the following define statement in a common header file before including <i>Ntddk.h</i>:

#define RTL_USE_AVL_TABLES 0

If RTL_USE_AVL_TABLES is not defined, you must use the AVL form of the generic table routines. For example, use the <b>RtlNumberGenericTableElementsAvl</b> routine instead of <a href="..\ntddk\nf-ntddk-rtlnumbergenerictableelements.md">RtlNumberGenericTableElements</a>. In the call to <b>RtlNumberGenericTableElementsAvl</b>, the caller must pass a <a href="..\ntddk\ns-ntddk-_rtl_avl_table.md">RTL_AVL_TABLE</a> table structure rather than <a href="..\ntddk\ns-ntddk-_rtl_generic_table.md">RTL_GENERIC_TABLE</a>.

Callers of the<i> Rtl..GenericTableAvl</i> routines are responsible for exclusively synchronizing access to the generic table. An exclusive fast mutex is the most efficient synchronization mechanism to use for this purpose. 

Callers of <b>RtlNumberGenericTableElementsAvl</b> must be running at IRQL &lt; DISPATCH_LEVEL if the caller-allocated memory for the generic table is pageable.



## -see-also

<a href="..\ntddk\nf-ntddk-rtlinitializegenerictableavl.md">RtlInitializeGenericTableAvl</a>

<a href="..\ntddk\nf-ntddk-rtlisgenerictableemptyavl.md">RtlIsGenericTableEmptyAvl</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlNumberGenericTableElementsAvl routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

