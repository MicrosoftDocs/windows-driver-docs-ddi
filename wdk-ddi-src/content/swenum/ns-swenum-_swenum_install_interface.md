---
UID: NS:swenum._SWENUM_INSTALL_INTERFACE
title: "_SWENUM_INSTALL_INTERFACE"
author: windows-driver-content
description: The SWENUM_INSTALL_INTERFACE structure describes a specific demand-load bus enumerator object interface to install.
old-location: stream\swenum_install_interface.htm
old-project: stream
ms.assetid: 05280f35-7728-464e-9a8a-e45ab797e8a9
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PSWENUM_INSTALL_INTERFACE, PSWENUM_INSTALL_INTERFACE, PSWENUM_INSTALL_INTERFACE structure pointer [Streaming Media Devices], SWENUM_INSTALL_INTERFACE, SWENUM_INSTALL_INTERFACE structure [Streaming Media Devices], _SWENUM_INSTALL_INTERFACE, ks-struct_64848a64-102a-44ec-b5d1-331526828c60.xml, stream.swenum_install_interface, swenum/PSWENUM_INSTALL_INTERFACE, swenum/SWENUM_INSTALL_INTERFACE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: swenum.h
req.include-header: Swenum.h
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
-	swenum.h
api_name:
-	SWENUM_INSTALL_INTERFACE
product: Windows
targetos: Windows
req.typenames: SWENUM_INSTALL_INTERFACE, *PSWENUM_INSTALL_INTERFACE
req.product: Windows 10 or later.
---

# _SWENUM_INSTALL_INTERFACE structure


## -description


The SWENUM_INSTALL_INTERFACE structure describes a specific demand-load bus enumerator object interface to install.


## -syntax


````
typedef struct _SWENUM_INSTALL_INTERFACE {
  GUID  DeviceId;
  GUID  InterfaceId;
  WCHAR ReferenceString[1];
} SWENUM_INSTALL_INTERFACE, *PSWENUM_INSTALL_INTERFACE;
````


## -struct-fields




### -field DeviceId

GUID that specifies the demand-load bus enumerator object's device ID.


### -field InterfaceId

GUID that specifies the demand-load bus enumerator object's interface ID.


### -field ReferenceString

A reference string that a driver can use to uniquely identify multiple interface instances of the same type for a single device.


## -remarks



The <i>swenum</i> driver uses device interface instances as placeholders for software devices created on demand.




## -see-also

<a href="..\swenum\nf-swenum-ksinstallbusenuminterface.md">KsInstallBusEnumInterface</a>



<a href="..\swenum\nf-swenum-ksremovebusenuminterface.md">KsRemoveBusEnumInterface</a>



 

 


