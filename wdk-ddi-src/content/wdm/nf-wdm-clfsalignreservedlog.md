---
UID: NF:wdm.ClfsAlignReservedLog
title: ClfsAlignReservedLog function
description: The ClfsAlignReservedLog routine calculates the size of the space that must be reserved for a specified set of records. The size calculation includes the space required for headers and the space required for sector alignment.
old-location: kernel\clfsalignreservedlog.htm
tech.root: kernel
ms.assetid: b79f58bb-af94-4143-9e30-6f50d85cbb3d
ms.date: 04/30/2018
ms.keywords: ClfsAlignReservedLog, ClfsAlignReservedLog routine [Kernel-Mode Driver Architecture], Clfs_68de31de-d1f9-4948-ab15-bf8678aebcf2.xml, kernel.clfsalignreservedlog, wdm/ClfsAlignReservedLog
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Server 2003 R2, Windows Vista, and later versions of Windows.
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
req.lib: Clfs.lib
req.dll: Clfs.sys
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Clfs.sys
-	Ext-MS-Win-fs-clfs-l1-1-0.dll
api_name:
-	ClfsAlignReservedLog
product:
- Windows
targetos: Windows
req.typenames: 
---

# ClfsAlignReservedLog function


## -description


The <b>ClfsAlignReservedLog</b> routine calculates the size of the space that must be reserved for a specified set of records. The size calculation includes the space required for headers and the space required for sector alignment.


## -parameters




### -param pvMarshalContext [in]

A pointer to an opaque context that represents a marshalling area associated with a CLFS stream. The caller previously obtained this pointer by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff541520">ClfsCreateMarshallingArea</a>.


### -param cRecords [in]

The number of elements in the array pointed to by <i>rgcbReservation</i>.


### -param rgcbReservation [in]

A pointer to an array of LONGLONG-typed variables that supplies a list of record sizes (in bytes).


### -param pcbAlignReservation [out]

A pointer to a LONGLONG-typed variable that receives the size, in bytes, of the required reservation.


## -returns



<b>ClfsAlignReservedLog</b> returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in Ntstatus.h. 




## -remarks



For an explanation of CLFS concepts and terminology, see <a href="https://msdn.microsoft.com/a9685648-b08c-48ca-b020-e683068f2ea2">Common Log File System</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540782">ClfsAllocReservedLog</a>
 

 

