---
UID: NC:ks.PFNKSINTERSECTHANDLEREX
title: PFNKSINTERSECTHANDLEREX (ks.h)
description: AVStream calls a minidriver's AVStrMiniIntersectHandlerEx routine to determine the highest quality intersection of two data ranges.
old-location: stream\avstrminiintersecthandlerex.htm
tech.root: stream
ms.assetid: d80f8bc6-29dc-4cb0-87f5-414ec6418156
ms.date: 04/23/2018
keywords: ["PFNKSINTERSECTHANDLEREX callback function"]
ms.keywords: AVStrMiniIntersectHandlerEx, AVStrMiniIntersectHandlerEx routine [Streaming Media Devices], PFNKSINTERSECTHANDLEREX, avstclbk_7a9be78c-3ca2-4fe2-961c-37dbd122a4b8.xml, ks/AVStrMiniIntersectHandlerEx, stream.avstrminiintersecthandlerex
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
targetos: Windows
req.typenames: 
f1_keywords:
 - PFNKSINTERSECTHANDLEREX
 - ks/PFNKSINTERSECTHANDLEREX
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - ks.h
api_name:
 - AVStrMiniIntersectHandlerEx
---

# PFNKSINTERSECTHANDLEREX callback function


## -description

AVStream calls a minidriver's <i>AVStrMiniIntersectHandlerEx</i> routine to determine the highest quality intersection of two data ranges.

## -parameters

### -param Context 

[in]
Pointer to the <b>Context</b> member of the corresponding <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilter">KSFILTER</a> structure.

### -param Irp 

[in]
Pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_irp">IRP</a> containing the intersection request.

### -param Pin 

[in]
Pointer to a structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksp_pin">KSP_PIN</a> that was passed in the intersection property request.

### -param DataRange 

[in]
Pointer to an array of <a href="https://docs.microsoft.com/previous-versions/ff561658(v=vs.85)">KSDATARANGE</a> structures.

### -param MatchingDataRange 

[in]
Pointer to an array of <a href="https://docs.microsoft.com/previous-versions/ff561658(v=vs.85)">KSDATARANGE</a> structures to match to <i>DataRange</i>.

### -param DataBufferSize 

[in]
Specifies a value of type ULONG that contains the size of the data buffer.

### -param Data 

[out]
Pointer to an optional data buffer in which the minidriver outputs the intersection.

### -param DataSize 

[out]
Pointer to a value of type ULONG specifying the size of the data buffer.

## -returns

If the callback finds a match, return STATUS_SUCCESS. Otherwise return STATUS_NO_MATCH.

## -remarks

The minidriver specifies this routine's address in the <b>IntersectHandler</b> member of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_kspin_descriptor_ex">KSPIN_DESCRIPTOR_EX</a> structure.

## -see-also

<a href="https://docs.microsoft.com/previous-versions/ff561658(v=vs.85)">KSDATARANGE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilter">KSFILTER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_kspin_descriptor_ex">KSPIN_DESCRIPTOR_EX</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-pin-dataintersection">KSPROPERTY_PIN_DATAINTERSECTION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksp_pin">KSP_PIN</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-kspindataintersectionex">KsPinDataIntersectionEx</a>

