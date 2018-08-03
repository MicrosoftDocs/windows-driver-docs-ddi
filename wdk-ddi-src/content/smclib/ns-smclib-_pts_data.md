---
UID: NS:smclib._PTS_DATA
title: "_PTS_DATA"
author: windows-driver-content
description: The PTS_DATA structure is used for protocol type selection (PTS).
old-location: smartcrd\pts_data.htm
tech.root: smartcrd
ms.assetid: aa542c6f-24f9-4ef4-a425-93905cca976a
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: "*PPTS_DATA, PPTS_DATA, PPTS_DATA structure pointer [Smart Card Reader Devices], PTS_DATA, PTS_DATA structure [Smart Card Reader Devices], _PTS_DATA, scstruct_8540d432-b29a-4227-a305-da7aba23a26d.xml, smartcrd.pts_data, smclib/PPTS_DATA, smclib/PTS_DATA"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: smclib.h
req.include-header: Smclib.h
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
-	smclib.h
api_name:
-	PTS_DATA
product:
- Windows
targetos: Windows
req.typenames: PTS_DATA, *PPTS_DATA
---

# _PTS_DATA structure


## -description


The PTS_DATA structure is used for protocol type selection (PTS).


## -struct-fields




### -field Type

Controls how the remaining members of this structure are calculated. This member can have one of the following values:





#### PTS_TYPE_DEFAULT

Calculates standard parameters for PTS.



#### PTS_TYPE_OPTIMAL

Calculates the best possible parameters for PTS.



#### PTS_TYPE_USER

Calculates user-defined parameters for PTS.

The smart card driver library populates the remaining members of this structure when the reader driver calls its <a href="https://msdn.microsoft.com/library/windows/hardware/ff548972">SmartcardUpdateCardCapabilities (WDM)</a> routine. However, in some cases, the reader driver might be responsible for setting these parameters. For example, if a PTS request that specifies optimal parameters fails, the reader driver can set the parameters in a callback function that specifies the protocol. To specify the protocol, the callback function should set the type to PTS_TYPE_DEFAULT and call <b>SmartcardUpdateCardCapabilities</b> again. 


### -field Fl

The Fl value to use as part of PTS1 for the PTS request.


### -field Dl

The Dl value to use as part of PTS1 for the PTS request.


### -field CLKFrequency

Contains the clock frequency. Some smart card readers must be programmed by using the new clock frequency to use after the PTS request.


### -field DataRate

Contains the new data rate. Some smart card readers (for example, serial readers) must be set to the new data rate to use after a PTS request.


### -field StopBits

Contains the number of stop bits to use with the inserted card.


## -remarks



The smart card reader driver library assigns values to the members of this structure before it calls the callback function that sets the protocol. The driver library considers the characteristics of the inserted smart card, the supported clock frequencies, and supported data rates of the reader when it assigns the values. 



