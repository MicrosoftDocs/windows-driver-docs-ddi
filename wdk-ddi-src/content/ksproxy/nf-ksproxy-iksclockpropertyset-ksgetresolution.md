---
UID: NF:ksproxy.IKsClockPropertySet.KsGetResolution
title: IKsClockPropertySet::KsGetResolution (ksproxy.h)
description: The KsGetResolution method retrieves the clock resolution from the underlying clock.
old-location: stream\iksclockpropertyset_ksgetresolution.htm
tech.root: stream
ms.assetid: 507d41ae-31b9-4807-99af-9ec48eb2b5aa
ms.date: 04/23/2018
keywords: ["IKsClockPropertySet::KsGetResolution"]
ms.keywords: IKsClockPropertySet interface [Streaming Media Devices],KsGetResolution method, IKsClockPropertySet.KsGetResolution, IKsClockPropertySet::KsGetResolution, KsGetResolution, KsGetResolution method [Streaming Media Devices], KsGetResolution method [Streaming Media Devices],IKsClockPropertySet interface, ksproxy/IKsClockPropertySet::KsGetResolution, ksproxy_0c0583b1-5ab3-4e30-bf99-6822d8966171.xml, stream.iksclockpropertyset_ksgetresolution
f1_keywords:
 - "ksproxy/IKsClockPropertySet.KsGetResolution"
 - "IKsClockPropertySet.KsGetResolution"
req.header: ksproxy.h
req.include-header: Ksproxy.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- ksproxy.h
api_name:
- IKsClockPropertySet.KsGetResolution
product:
- Windows
targetos: Windows
req.typenames: 
---

# IKsClockPropertySet::KsGetResolution


## -description


The <b>KsGetResolution</b> method retrieves the clock resolution from the underlying clock.


## -parameters




### -param Resolution [out]

Pointer to a variable that receives a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksresolution">KSRESOLUTION</a> structure that contains the granularity and error of the underlying clock.


## -returns



Returns NOERROR if successful; otherwise, returns an error code.




## -remarks



The <b>KsGetResolution</b> method retrieves the underlying clock's resolution property, which specifies the underlying clock's increment granularity and notification error in terms of 100-nanosecond units. The best granularity would be one 100-nanosecond unit; less granular increments would contain larger numbers. The least amount of notification error above and beyond the clock granularity would be reported as zero 100-nanosecond units, and less accurate clocks would use larger numbers to indicate +/− error. The proxy can use this resolution property to determine maximum error and resolution in event notification and synchronization.

The proxy uses the <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-clock-resolution">KSPROPERTY_CLOCK_RESOLUTION</a> property to retrieve the clock resolution. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-clock-resolution">KSPROPERTY_CLOCK_RESOLUTION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksresolution">KSRESOLUTION</a>
 

 

