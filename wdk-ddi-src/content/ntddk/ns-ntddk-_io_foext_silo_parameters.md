---
UID: NS:ntddk._IO_FOEXT_SILO_PARAMETERS
title: "_IO_FOEXT_SILO_PARAMETERS"
author: windows-driver-content
description: This structure describes the Container context that's identified by the IoGetSiloParameters routine.
old-location: ifsk\io_foext_silo_parameters.htm
old-project: ifsk
ms.assetid: EC7C59D0-96AE-400D-9502-D6DBFD9918DC
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: PIO_FOEXT_SILO_PARAMETERS structure pointer [Installable File System Drivers], PIO_FOEXT_SILO_PARAMETERS, IO_FOEXT_SILO_PARAMETERS, IO_FOEXT_SILO_PARAMETERS structure [Installable File System Drivers], ntddk/PIO_FOEXT_SILO_PARAMETERS, ntddk/IO_FOEXT_SILO_PARAMETERS, *PIO_FOEXT_SILO_PARAMETERS, ifsk.io_foext_silo_parameters, _IO_FOEXT_SILO_PARAMETERS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddk.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1607
req.target-min-winversvr: Windows Server 2016
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
-	HeaderDef
apilocation:
-	ntddk.h
apiname:
-	IO_FOEXT_SILO_PARAMETERS
product: Windows
targetos: Windows
req.typenames: IO_FOEXT_SILO_PARAMETERS, *PIO_FOEXT_SILO_PARAMETERS
---

# _IO_FOEXT_SILO_PARAMETERS structure


## -description


This structure describes the Container context that's identified by the <a href="..\ntddk\nf-ntddk-iogetsiloparameters.md">IoGetSiloParameters</a> routine.


## -syntax


````
typedef struct _IO_FOEXT_SILO_PARAMETERS {
  ULONG  Length;
  PESILO SiloContext;
} IO_FOEXT_SILO_PARAMETERS, *PIO_FOEXT_SILO_PARAMETERS;
````


## -struct-fields




### -field Length

The length of the structure. This also serves as the structure version.


### -field HasHardReference

 


### -field SpareFlags

 


### -field SiloContext

The container context.

