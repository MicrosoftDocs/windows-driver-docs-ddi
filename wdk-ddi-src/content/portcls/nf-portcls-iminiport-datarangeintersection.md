---
UID: NF:portcls.IMiniport.DataRangeIntersection
title: IMiniport::DataRangeIntersection (portcls.h)
description: TBD
tech.root: audio
ms.assetid: 4426949b-74c5-48b4-8a06-fad96a8ab743
ms.date: 12/28/2018
ms.topic: method
ms.keywords: IMiniport::DataRangeIntersection, DataRangeIntersection, IMiniport.DataRangeIntersection, IMiniport::DataRangeIntersection, IMiniport.DataRangeIntersection
req.header: portcls.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: PASSIVE_LEVEL
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
 - apiref
api_type: 
 - COM
api_location: 
 - portcls.h
api_name: 
 - IMiniport.DataRangeIntersection
product: 
 - Windows
targetos: Windows

---

# IMiniport::DataRangeIntersection


## -description

The DataRangeIntersection method determines the highest quality intersection of two data ranges.

## -parameters

### -param PinId
Specifies the pin ID. This parameter identifies the pin factory for which the data intersection is being determined. If the filter contains n pin factories, valid pin IDs range from 0 to n-1.

### -param DataRange
Pointer to a KSDATARANGE structure that contains the data range submitted by the client in the data-range intersection property request.

### -param MatchingDataRange
Pointer to a KSDATARANGE structure that contains the miniport driver's data range that is to be compared to the client's data range.


### -param OutputBufferLength
Specifies the size in bytes of the buffer pointed to by the ResultantFormat parameter. The caller can specify OutputBufferLength as zero to query for the required buffer size. For more information, see the following Remarks section.


### -param ResultantFormat
Pointer to the buffer into which the method writes the resultant format. If this parameter is NULL, the OutputBufferLength parameter must be zero. If non-NULL, this parameter must point to a buffer that is large enough to contain the number bytes specified in OutputBufferLength.


### -param ResultantFormatLength
Output pointer for the resultant-format length. This parameter points to a caller-allocated ULONG variable into which the method writes the length of the resultant format. This is the size in bytes of the resultant format that is written to the buffer pointed to by ResultantFormat. This size must be less than or equal to OutputBufferLength (unless OutputBufferLength is zero; see the following Remarks section).


## -returns
This method returns NTSTATUS which contains STATUS_SUCCESS if the call was successful. If the OutputBufferLength parameter was specified as zero, the method returns STATUS_BUFFER_OVERFLOW. Otherwise, the method returns an appropriate error code. The following table shows some of the possible return status codes.

Return code | Description
------------|------------- 
STATUS_NO_MATCH | There is no intersection.
STATUS_NOT_IMPLEMENTED | Defers data-intersection handling to the port driver's default data-intersection handler.
STATUS_BUFFER_TOO_SMALL | The buffer length specified in OutputBufferLength was nonzero but was too small to hold the resultant format.


## -remarks
The DataRangeIntersection method is the miniport driver's data-intersection handler. The port driver calls this method when it receives a data-range intersection property request (see KSPROPERTY_PIN_DATAINTERSECTION) and the target for the request is a pin factory on a filter instance that the miniport driver implements.

The ResultantFormat parameter points to a buffer that begins with a KSDATAFORMAT_WAVEFORMATEX structure. Note that the WaveFormatEx member of this structure can be extended to include additional format information (for example, a channel configuration mask). For more information, see [WAVEFORMATEXTENSIBLE](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ksmedia/ns-ksmedia-waveformatextensible).

The ResultantFormat parameter is optional and can be specified as NULL, in which case OutputBufferLength must be specified as zero. The caller can query for the required buffer length by making an initial call to DataRangeIntersection with an OutputBufferLength value of zero. The method responds by writing the required buffer length to the location pointed to by ResultantFormatLength and returning status code STATUS_BUFFER_OVERFLOW. The caller can then allocate a buffer of the required size and specify this buffer in a second call to DataRangeIntersection.

If the driver supports KSPROPERTY_AUDIOSIGNALPROCESSING_MODES, this method shall return *ResultantFormat* if the format is supported by any Audio signal processing mode. 

## -see-also

[IMiniPort](nn-portcls-iminiport.md)
