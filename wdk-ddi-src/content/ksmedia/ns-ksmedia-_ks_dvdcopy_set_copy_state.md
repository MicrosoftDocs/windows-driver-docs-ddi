---
UID: NS:ksmedia._KS_DVDCOPY_SET_COPY_STATE
title: _KS_DVDCOPY_SET_COPY_STATE
author: windows-driver-content
description: The KS_DVDCOPY_SET_COPY_STATE structure is used to specify the copyright protection state of the DVD decoder stream.
old-location: stream\ks_dvdcopy_set_copy_state.htm
old-project: stream
ms.assetid: e4f637b7-52ce-4ec8-8348-0b65a7f788ad
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: _KS_DVDCOPY_SET_COPY_STATE, *PKS_DVDCOPY_SET_COPY_STATE, KS_DVDCOPY_SET_COPY_STATE
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
req.alt-api: KS_DVDCOPY_SET_COPY_STATE
req.alt-loc: ksmedia.h
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
req.typenames: *PKS_DVDCOPY_SET_COPY_STATE, KS_DVDCOPY_SET_COPY_STATE
---

# _KS_DVDCOPY_SET_COPY_STATE structure



## -description
The KS_DVDCOPY_SET_COPY_STATE structure is used to specify the copyright protection state of the DVD decoder stream.



## -syntax

````
typedef struct _KS_DVDCOPY_SET_COPY_STATE {
  ULONG DVDCopyState;
} KS_DVDCOPY_SET_COPY_STATE, *PKS_DVDCOPY_SET_COPY_STATE;
````


## -struct-fields

### -field DVDCopyState

Indicates the progress of the copyright protection initialization, authentication and key negotiation sequence. This must be one of the values from the <a href="..\ksmedia\ne-ksmedia-ks_dvdcopystate.md">KS_DVDCOPYSTATE</a> enumeration.


## -remarks
This structure is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565147">KSPROPERTY_DVDCOPY_SET_COPY_STATE</a> property.

For more information, see <a href="https://msdn.microsoft.com/ff9cf8c8-7c8f-485c-b2ab-7567a5eeb87b">DVD Copyright Protection</a>, <a href="https://msdn.microsoft.com/23133022-6d00-44ad-8c0d-24715204cacc">Multiple Data Streams on the same Hardware</a> and <a href="https://msdn.microsoft.com/54abc258-d26a-4d42-a5aa-712cdae76b6d">Synchronizing Key Exchange with Data Flow</a>.


## -see-also
<dl>
<dt>
<a href="..\ksmedia\ne-ksmedia-ks_dvdcopystate.md">KS_DVDCOPYSTATE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565147">KSPROPERTY_DVDCOPY_SET_COPY_STATE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KS_DVDCOPY_SET_COPY_STATE structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

