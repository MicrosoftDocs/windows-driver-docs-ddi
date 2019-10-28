---
UID: NF:ks.KsPinGetConnectedPinFileObject
title: KsPinGetConnectedPinFileObject function (ks.h)
description: The KsPinGetConnectedPinFileObject function returns the file object for the pin to which Pin is connected. Works only for source pins.
old-location: stream\kspingetconnectedpinfileobject.htm
tech.root: stream
ms.assetid: 1025c89f-8d63-4aeb-be7c-16b555cfa58a
ms.date: 04/23/2018
ms.keywords: KsPinGetConnectedPinFileObject, KsPinGetConnectedPinFileObject function [Streaming Media Devices], avfunc_af97a9b7-4bf9-4faa-a728-099daf7d4c96.xml, ks/KsPinGetConnectedPinFileObject, stream.kspingetconnectedpinfileobject
ms.topic: function
f1_keywords:
 - "ks/KsPinGetConnectedPinFileObject"
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
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
req.lib: Ks.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Ks.lib
- Ks.dll
api_name:
- KsPinGetConnectedPinFileObject
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsPinGetConnectedPinFileObject function


## -description


The<b> KsPinGetConnectedPinFileObject </b>function returns the file object for the pin to which <i>Pin</i> is connected. Works only for source pins.


## -parameters




### -param Pin [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_kspin">KSPIN</a> structure that is the AVStream pin object for which to acquire the file object for the connected pin.


## -returns



If <i>Pin</i> is a source pin, <b>KsPinGetConnectedPinFileObject</b> returns a pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_object">FILE_OBJECT</a> structure for the pin to which <i>Pin</i> is connected. If <i>Pin</i> is not a source pin, it returns <b>NULL</b>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-kspingetconnectedfilterinterface">KsPinGetConnectedFilterInterface</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-kspingetconnectedpininterface">KsPinGetConnectedPinInterface</a>
 

 

