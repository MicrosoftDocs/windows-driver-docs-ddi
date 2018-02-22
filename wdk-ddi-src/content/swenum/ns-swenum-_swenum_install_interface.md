---
UID: NS:swenum._SWENUM_INSTALL_INTERFACE
title: "_SWENUM_INSTALL_INTERFACE"
author: windows-driver-content
description: The SWENUM_INSTALL_INTERFACE structure describes a specific demand-load bus enumerator object interface to install.
old-location: stream\swenum_install_interface.htm
old-project: stream
ms.assetid: 05280f35-7728-464e-9a8a-e45ab797e8a9
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: SWENUM_INSTALL_INTERFACE, swenum/SWENUM_INSTALL_INTERFACE, SWENUM_INSTALL_INTERFACE structure [Streaming Media Devices], swenum/PSWENUM_INSTALL_INTERFACE, *PSWENUM_INSTALL_INTERFACE, PSWENUM_INSTALL_INTERFACE structure pointer [Streaming Media Devices], _SWENUM_INSTALL_INTERFACE, ks-struct_64848a64-102a-44ec-b5d1-331526828c60.xml, PSWENUM_INSTALL_INTERFACE, stream.swenum_install_interface
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	swenum.h
apiname:
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



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20SWENUM_INSTALL_INTERFACE structure%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

