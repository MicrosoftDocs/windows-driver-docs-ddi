---
UID: NE:portcls.eEngineFormatType
title: eEngineFormatType
author: windows-driver-content
description: The eEngineFormatType enumeration defines constants that specify the audio data type supported by the audio engine.
old-location: audio\eengineformattype.htm
old-project: audio
ms.assetid: C16DE51F-6552-4379-B866-D7653B1BA9F2
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: eSupportedDeviceFormats, portcls/eEngineFormatType, eDeviceFormat, portcls/eDeviceFormat, audio.eengineformattype, eMixFormat, portcls/eSupportedDeviceFormats, eEngineFormatType enumeration [Audio Devices], portcls/eMixFormat, eEngineFormatType
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: portcls.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	Portcls.h
apiname:
-	eEngineFormatType
product: Windows
targetos: Windows
req.typenames: eEngineFormatType
---

# eEngineFormatType enumeration


## -description


The <b>eEngineFormatType</b> enumeration defines constants that specify the audio data type supported by the audio engine.


## -syntax


````
typedef enum _eEngineFormatType { 
  eMixFormat,
  eDeviceFormat,
  eSupportedDeviceFormats
} eEngineFormatType;
````


## -enum-fields




### -field eMixFormat

Indicates a data format for the Mixer.


### -field eDeviceFormat

Indicates the default data format for the audio adapter.


### -field eSupportedDeviceFormats

Indicates all the data formats supported by the audio adapter.


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn265082">GetEngineFormatSize</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20eEngineFormatType enumeration%20 RELEASE:%20(2/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

