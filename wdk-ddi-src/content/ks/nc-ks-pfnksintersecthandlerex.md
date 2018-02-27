---
UID: NC:ks.PFNKSINTERSECTHANDLEREX
title: PFNKSINTERSECTHANDLEREX
author: windows-driver-content
description: AVStream calls a minidriver's AVStrMiniIntersectHandlerEx routine to determine the highest quality intersection of two data ranges.
old-location: stream\avstrminiintersecthandlerex.htm
old-project: stream
ms.assetid: d80f8bc6-29dc-4cb0-87f5-414ec6418156
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: AVStrMiniIntersectHandlerEx, AVStrMiniIntersectHandlerEx routine [Streaming Media Devices], PFNKSINTERSECTHANDLEREX, avstclbk_7a9be78c-3ca2-4fe2-961c-37dbd122a4b8.xml, ks/AVStrMiniIntersectHandlerEx, stream.avstrminiintersecthandlerex
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ks.h
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
req.lib: 
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	ks.h
apiname:
-	AVStrMiniIntersectHandlerEx
product: Windows
targetos: Windows
req.typenames: SOUNDDETECTOR_PATTERNHEADER
---

# PFNKSINTERSECTHANDLEREX callback


## -description


AVStream calls a minidriver's <i>AVStrMiniIntersectHandlerEx</i> routine to determine the highest quality intersection of two data ranges.


## -prototype


````
PFNKSINTERSECTHANDLEREX AVStrMiniIntersectHandlerEx;

NTSTATUS AVStrMiniIntersectHandlerEx(
  _In_  PVOID        Context,
  _In_  PIRP         Irp,
  _In_  PKSP_PIN     Pin,
  _In_  PKSDATARANGE DataRange,
  _In_  PKSDATARANGE MatchingDataRange,
  _In_  ULONG        DataBufferSize,
  _Out_ PVOID        Data,
  _Out_ PULONG       DataSize
)
{ ... }
````


## -parameters




### -param Context [in]

Pointer to the <b>Context</b> member of the corresponding <a href="..\ks\ns-ks-_ksfilter.md">KSFILTER</a> structure.


### -param Irp [in]

Pointer to the <a href="..\wdm\ns-wdm-_irp.md">IRP</a> containing the intersection request.


### -param Pin [in]

Pointer to a structure of type <a href="..\ks\ns-ks-ksp_pin.md">KSP_PIN</a> that was passed in the intersection property request.


### -param DataRange [in]

Pointer to an array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff561658">KSDATARANGE</a> structures.


### -param MatchingDataRange [in]

Pointer to an array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff561658">KSDATARANGE</a> structures to match to <i>DataRange</i>.


### -param DataBufferSize [in]

Specifies a value of type ULONG that contains the size of the data buffer.


### -param Data [out]

Pointer to an optional data buffer in which the minidriver outputs the intersection.


### -param DataSize [out]

Pointer to a value of type ULONG specifying the size of the data buffer.


## -returns



If the callback finds a match, return STATUS_SUCCESS. Otherwise return STATUS_NO_MATCH.




## -remarks



The minidriver specifies this routine's address in the <b>IntersectHandler</b> member of a <a href="..\ks\ns-ks-_kspin_descriptor_ex.md">KSPIN_DESCRIPTOR_EX</a> structure.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff561658">KSDATARANGE</a>



<a href="..\ks\ns-ks-_kspin_descriptor_ex.md">KSPIN_DESCRIPTOR_EX</a>



<a href="..\ks\ns-ks-ksp_pin.md">KSP_PIN</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565198">KSPROPERTY_PIN_DATAINTERSECTION</a>



<a href="..\ks\ns-ks-_ksfilter.md">KSFILTER</a>



<a href="..\ks\nf-ks-kspindataintersectionex.md">KsPinDataIntersectionEx</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20PFNKSINTERSECTHANDLEREX routine%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

