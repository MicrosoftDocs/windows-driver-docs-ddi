---
UID: NE:ksmedia.KS_DVDCOPYSTATE
title: KS_DVDCOPYSTATE
author: windows-driver-content
description: The KS_DVDCOPYSTATE enumeration describes the progress of the DVD copyright protection initialization, authentication and key negotiation sequence.
old-location: stream\ks_dvdcopystate.htm
old-project: stream
ms.assetid: 4072eaf1-d4cc-4255-90c1-177d6d58bb0a
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: KS_DVDCOPYSTATE_INITIALIZE, ksmedia/KS_DVDCOPYSTATE_INITIALIZE_TITLE, KS_DVDCOPYSTATE, stream.ks_dvdcopystate, KS_DVDCOPYSTATE_DONE, KS_DVDCOPYSTATE_AUTHENTICATION_NOT_REQUIRED, ksmedia/KS_DVDCOPYSTATE_AUTHENTICATION_REQUIRED, ksmedia/KS_DVDCOPYSTATE_DONE, dvdref_f91c9ef4-f31c-4065-8017-26ef6ef76708.xml, ksmedia/KS_DVDCOPYSTATE_AUTHENTICATION_NOT_REQUIRED, ksmedia/KS_DVDCOPYSTATE_INITIALIZE, KS_DVDCOPYSTATE_INITIALIZE_TITLE, ksmedia/KS_DVDCOPYSTATE, KS_DVDCOPYSTATE enumeration [Streaming Media Devices], KS_DVDCOPYSTATE_AUTHENTICATION_REQUIRED
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ksmedia.h
apiname:
-	KS_DVDCOPYSTATE
product: Windows
targetos: Windows
req.typenames: KS_DVDCOPYSTATE
---

# KS_DVDCOPYSTATE enumeration


## -description


The KS_DVDCOPYSTATE enumeration describes the progress of the DVD copyright protection initialization, authentication and key negotiation sequence.


## -syntax


````
typedef enum  { 
  KS_DVDCOPYSTATE_INITIALIZE                   = 0,
  KS_DVDCOPYSTATE_INITIALIZE_TITLE             = 1,
  KS_DVDCOPYSTATE_AUTHENTICATION_NOT_REQUIRED  = 2,
  KS_DVDCOPYSTATE_AUTHENTICATION_REQUIRED      = 3,
  KS_DVDCOPYSTATE_DONE                         = 4
} KS_DVDCOPYSTATE;
````


## -enum-fields




### -field KS_DVDCOPYSTATE_INITIALIZE

Indicates that the full copyright protection sequence is starting.


### -field KS_DVDCOPYSTATE_INITIALIZE_TITLE

Indicates that a title key copyright protection sequence is starting.


### -field KS_DVDCOPYSTATE_AUTHENTICATION_NOT_REQUIRED

Indicates that no authentication is required.


### -field KS_DVDCOPYSTATE_AUTHENTICATION_REQUIRED

Indicates that authentication is required.


### -field KS_DVDCOPYSTATE_DONE

Indicates that the copyright protection sequence is complete.


## -see-also

<a href="..\ksmedia\ns-ksmedia-_ks_dvdcopy_set_copy_state.md">KS_DVDCOPY_SET_COPY_STATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565147">KSPROPERTY_DVDCOPY_SET_COPY_STATE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KS_DVDCOPYSTATE enumeration%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

