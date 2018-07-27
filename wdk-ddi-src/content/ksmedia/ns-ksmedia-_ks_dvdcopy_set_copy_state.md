---
UID: NS:ksmedia._KS_DVDCOPY_SET_COPY_STATE
title: "_KS_DVDCOPY_SET_COPY_STATE"
author: windows-driver-content
description: The KS_DVDCOPY_SET_COPY_STATE structure is used to specify the copyright protection state of the DVD decoder stream.
old-location: stream\ks_dvdcopy_set_copy_state.htm
tech.root: stream
ms.assetid: e4f637b7-52ce-4ec8-8348-0b65a7f788ad
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: "*PKS_DVDCOPY_SET_COPY_STATE, KS_DVDCOPY_SET_COPY_STATE, KS_DVDCOPY_SET_COPY_STATE structure [Streaming Media Devices], PKS_DVDCOPY_SET_COPY_STATE, PKS_DVDCOPY_SET_COPY_STATE structure pointer [Streaming Media Devices], _KS_DVDCOPY_SET_COPY_STATE, dvdref_215efe26-9ca5-4f3b-836f-86a682cd88f8.xml, ksmedia/KS_DVDCOPY_SET_COPY_STATE, ksmedia/PKS_DVDCOPY_SET_COPY_STATE, stream.ks_dvdcopy_set_copy_state"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.target-type: Windows
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ksmedia.h
api_name:
-	KS_DVDCOPY_SET_COPY_STATE
product:
- Windows
targetos: Windows
req.typenames: KS_DVDCOPY_SET_COPY_STATE, *PKS_DVDCOPY_SET_COPY_STATE
---

# _KS_DVDCOPY_SET_COPY_STATE structure


## -description


The KS_DVDCOPY_SET_COPY_STATE structure is used to specify the copyright protection state of the DVD decoder stream.


## -struct-fields




### -field DVDCopyState

Indicates the progress of the copyright protection initialization, authentication and key negotiation sequence. This must be one of the values from the <a href="https://msdn.microsoft.com/library/windows/hardware/ff567634">KS_DVDCOPYSTATE</a> enumeration.


## -remarks



This structure is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565147">KSPROPERTY_DVDCOPY_SET_COPY_STATE</a> property.

For more information, see <a href="https://msdn.microsoft.com/ff9cf8c8-7c8f-485c-b2ab-7567a5eeb87b">DVD Copyright Protection</a>, <a href="https://msdn.microsoft.com/23133022-6d00-44ad-8c0d-24715204cacc">Multiple Data Streams on the same Hardware</a> and <a href="https://msdn.microsoft.com/54abc258-d26a-4d42-a5aa-712cdae76b6d">Synchronizing Key Exchange with Data Flow</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff565147">KSPROPERTY_DVDCOPY_SET_COPY_STATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567634">KS_DVDCOPYSTATE</a>
 

 

