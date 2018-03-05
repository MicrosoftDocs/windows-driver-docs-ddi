---
UID: NS:avcstrm.tagKS_DATAFORMAT_DV_AVC
title: tagKS_DATAFORMAT_DV_AVC
author: windows-driver-content
description: The KS_DATAFORMAT_DV_AVC structure stores the data format for an AV/C digital video connection.
old-location: stream\ks_dataformat_dv_avc.htm
old-project: stream
ms.assetid: fe545ee3-8004-46fc-a49a-4274f8d1a6a7
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PKS_DATAFORMAT_DV_AVC, KS_DATAFORMAT_DV_AVC, KS_DATAFORMAT_DV_AVC structure [Streaming Media Devices], PKS_DATAFORMAT_DV_AVC, PKS_DATAFORMAT_DV_AVC structure pointer [Streaming Media Devices], avcsref_36d913e1-7071-46db-849d-2493fa30aad8.xml, avcstrm/KS_DATAFORMAT_DV_AVC, avcstrm/PKS_DATAFORMAT_DV_AVC, stream.ks_dataformat_dv_avc, tagKS_DATAFORMAT_DV_AVC"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: avcstrm.h
req.include-header: Avcstrm.h
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
-	avcstrm.h
api_name:
-	KS_DATAFORMAT_DV_AVC
product: Windows
targetos: Windows
req.typenames: KS_DATAFORMAT_DV_AVC, *PKS_DATAFORMAT_DV_AVC
---

# tagKS_DATAFORMAT_DV_AVC structure


## -description


The KS_DATAFORMAT_DV_AVC structure stores the data format for an AV/C digital video connection.


## -syntax


````
typedef struct tagKS_DATAFORMAT_DV_AVC {
  KSDATAFORMAT   DataFormat;
  DVINFO         DVVideoInfo;
  AVCCONNECTINFO ConnectInfo;
} KS_DATAFORMAT_DV_AVC, *PKS_DATAFORMAT_DV_AVC;
````


## -struct-fields




### -field DataFormat

Specifies the data format of the digital video connection.


### -field DVVideoInfo

Specifies the digital video information, for example, sound tracks and video information.


### -field ConnectInfo

Specifies the AV/C connection information.


## -see-also

<a href="..\ks\ns-ks-ksdataformat.md">KSDATAFORMAT</a>



<a href="..\avc\ns-avc-_avcconnectinfo.md">AVCCONNECTINFO</a>



<a href="..\avcstrm\ns-avcstrm-_dvinfo.md">DVINFO</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KS_DATAFORMAT_DV_AVC structure%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

