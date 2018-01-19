---
UID: NF:irb.AtaPortBusChangeDetected
title: AtaPortBusChangeDetected function
author: windows-driver-content
description: The AtaPortBusChangeDetected routine notifies the port driver of changes in the device configuration on the indicated channel.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportbuschangedetected.htm
old-project: storage
ms.assetid: e5a3d4dc-7446-49c1-985a-9d3a9d43dc15
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: AtaPortBusChangeDetected
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: irb.h
req.include-header: Ata.h, Irb.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: AtaPortBusChangeDetected
req.alt-loc: Irb.h
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
req.typenames: IDE_POWER_STATE
---

# AtaPortBusChangeDetected function



## -description
The <b>AtaPortBusChangeDetected</b> routine notifies the port driver of changes in the device configuration on the indicated channel.



## -syntax

````
VOID AtaPortBusChangeDetected(
   IN PVOID ChannelExtension
);
````


## -parameters

### -param ChannelExtension 

A pointer to the channel extension. 


## -returns
None 


## -remarks
The miniport driver uses this routine to report the arrival or removal of any device that is attached to the channel. In response, the port driver will initiate a re-scan to discover and initialize the device. </p>