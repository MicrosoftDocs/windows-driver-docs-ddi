---
UID: NC:ks.PFNKSPINSETDATAFORMAT
title: PFNKSPINSETDATAFORMAT
author: windows-driver-content
description: An AVStream minidriver's AVStrMiniPinSetDataFormat routine is called at pin creation time to verify that the previously agreed upon data format is acceptable for this KSPIN structure and a match for this KSDATARANGE structure.
old-location: stream\avstrminipinsetdataformat.htm
old-project: stream
ms.assetid: f38222e8-f432-4a28-ba2f-2e4f60edd762
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: AVStrMiniPinSetDataFormat, AVStrMiniPinSetDataFormat routine [Streaming Media Devices], PFNKSPINSETDATAFORMAT, avstclbk_c72cee40-d3d3-45df-8ece-2eb0a8b52e38.xml, ks/AVStrMiniPinSetDataFormat, stream.avstrminipinsetdataformat
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ks.h
req.include-header: Ks.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	ks.h
apiname:
-	AVStrMiniPinSetDataFormat
product: Windows
targetos: Windows
req.typenames: SOUNDDETECTOR_PATTERNHEADER
---

# PFNKSPINSETDATAFORMAT callback


## -description


An AVStream minidriver's <i>AVStrMiniPinSetDataFormat</i> routine is called at pin creation time to verify that the previously agreed upon data format is acceptable for this <a href="..\ks\ns-ks-_kspin.md">KSPIN</a> structure and a match for this <a href="https://msdn.microsoft.com/library/windows/hardware/ff561658">KSDATARANGE</a> structure. This routine is also called due to certain types of dynamic format changes, for example the acceptance of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff565107">KSPROPERTY_CONNECTION_PROPOSEDATAFORMAT</a> property request.


## -prototype


````
PFNKSPINSETDATAFORMAT AVStrMiniPinSetDataFormat;

NTSTATUS AVStrMiniPinSetDataFormat(
  _In_           PKSPIN           Pin,
  _In_opt_       PKSDATAFORMAT    OldFormat,
  _In_opt_       PKSMULTIPLE_ITEM OldAttributeList,
  _In_     const KSDATARANGE      *DataRange,
  _In_opt_ const KSATTRIBUTE_LIST *AttributeRange
)
{ ... }
````


## -parameters




### -param Pin [in]

Pointer to the <a href="..\ks\ns-ks-_kspin.md">KSPIN</a> structure for which the data format is changing.


### -param OldFormat [in, optional]

Optional. Pointer to a <a href="..\ks\ns-ks-ksdataformat.md">KSDATAFORMAT</a> structure. Minidrivers can use this field to determine the data format that the pin was using before this call. If <b>NULL</b>, indicates that no data format has been set for the pin and that <i>Pin's</i> create dispatch has not yet been made. A <b>NULL</b> value here indicates that this routine was called at initialization time for format verification.


### -param OldAttributeList [in, optional]

Optional. Pointer to a <a href="..\ks\ns-ks-ksmultiple_item.md">KSMULTIPLE_ITEM</a> structure that stores attributes for the previous format.


### -param *DataRange [in]

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff561658">KSDATARANGE</a> structure. The data range for the new format.


### -param *AttributeRange [in, optional]

Optional. The attribute range for the new format.


## -returns



Return STATUS_SUCCESS if <i>Pin</i>'s <b>ConnectionFormat</b> member matches the range that was passed to this routine. Return STATUS_NO_MATCH if <b>ConnectionFormat</b> does not match the passed range and the minidriver would like to continue to attempt to find a match with another range. Return an error code of choice if <b>ConnectionFormat</b> does not match the passed range and the minidriver does not want to continue to try to find a match with another range. Do not return STATUS_PENDING.




## -remarks



In a ring 3 graph, the Kernel Streaming Proxy module (KsProxy) sets the data format based on the agreed upon connection format or a dynamic format change. KsProxy issues a <a href="https://msdn.microsoft.com/library/windows/hardware/ff565103">KSPROPERTY_CONNECTION_DATAFORMAT</a> request which, after some initial validation, is translated into this dispatch call to the minidriver. See <a href="https://msdn.microsoft.com/94ca96ae-d6de-4764-b95f-d3784af40e4d">Kernel Streaming Proxy</a>. For more information, see <a href="https://msdn.microsoft.com/44b55a5a-ec58-4c1e-b780-e20829fe3edf">KS Data Formats and Data Ranges</a> and <a href="https://msdn.microsoft.com/44281574-8258-47a3-857d-fd44bb949f17">DataRange Intersections in AVStream</a>.

The minidriver specifies the address for <i>AVStrMiniPinSetDataFormat</i> in the <b>SetDataFormat</b> member of its <a href="..\ks\ns-ks-_kspin_dispatch.md">KSPIN_DISPATCH</a> structure.

This routine can be called before the pin receives an <a href="https://msdn.microsoft.com/library/windows/hardware/ff548630">IRP_MJ_CREATE</a>, and minidrivers should be prepared to deal with this situation.

<i>OldFormat</i>, <i>OldAttributeList</i>, and <i>AttributeRange</i> are all optional parameters and can be <b>NULL</b>. 

This routine is optional.




## -see-also

<a href="..\ks\ns-ks-_kspin_dispatch.md">KSPIN_DISPATCH</a>



<a href="..\ks\ns-ks-ksmultiple_item.md">KSMULTIPLE_ITEM</a>



<a href="..\ks\ns-ks-_kspin.md">KSPIN</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561658">KSDATARANGE</a>



<a href="..\ks\ns-ks-ksdataformat.md">KSDATAFORMAT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548630">IRP_MJ_CREATE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20PFNKSPINSETDATAFORMAT routine%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

