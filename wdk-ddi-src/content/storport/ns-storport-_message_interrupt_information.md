---
UID: NS:storport._MESSAGE_INTERRUPT_INFORMATION
title: "_MESSAGE_INTERRUPT_INFORMATION"
author: windows-driver-content
description: The MESSAGE_INTERRUPT_INFORMATION structure describes a message signaled interrupt (MSI).
old-location: storage\message_interrupt_information.htm
old-project: storage
ms.assetid: 469896b3-3ae0-4edd-9fb0-ee5869633872
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: MESSAGE_INTERRUPT_INFORMATION, storport/PMESSAGE_INTERRUPT_INFORMATION, PMESSAGE_INTERRUPT_INFORMATION, structs-storport_a918acbf-24eb-4112-8bab-bb2ee441064e.xml, PMESSAGE_INTERRUPT_INFORMATION structure pointer [Storage Devices], _MESSAGE_INTERRUPT_INFORMATION, storport/MESSAGE_INTERRUPT_INFORMATION, *PMESSAGE_INTERRUPT_INFORMATION, MESSAGE_INTERRUPT_INFORMATION structure [Storage Devices], storage.message_interrupt_information
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: storport.h
req.include-header: Storport.h
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
-	storport.h
apiname:
-	MESSAGE_INTERRUPT_INFORMATION
product: Windows
targetos: Windows
req.typenames: "*PMESSAGE_INTERRUPT_INFORMATION, MESSAGE_INTERRUPT_INFORMATION"
req.product: Windows 10 or later.
---

# _MESSAGE_INTERRUPT_INFORMATION structure


## -description


The <b>MESSAGE_INTERRUPT_INFORMATION</b> structure describes a message signaled interrupt (MSI).


## -syntax


````
typedef struct _MESSAGE_INTERRUPT_INFORMATION {
  ULONG                 MessageId;
  ULONG                 MessageData;
  STOR_PHYSICAL_ADDRESS MessageAddress;
  ULONG                 InterruptVector;
  ULONG                 InterruptLevel;
  KINTERRUPT_MODE       InterruptMode;
} MESSAGE_INTERRUPT_INFORMATION, *PMESSAGE_INTERRUPT_INFORMATION;
````


## -struct-fields




### -field MessageId

An identifier identifies the MSI interrupt. A miniport driver can pass this value to <a href="..\storport\nf-storport-storportacquiremsispinlock.md">StorPortAcquireMSISpinLock</a> in the <i>MessageId</i> parameter to obtain a spin lock for synchronization purposes. 


### -field MessageData

The data associated with the message. 


### -field MessageAddress

The physical address associated with the message. 


### -field InterruptVector

The interrupt vector associated with the message. 


### -field InterruptLevel

The interrupt level associated with the message. 


### -field InterruptMode

A value of type <a href="..\wdm\ne-wdm-_kinterrupt_mode.md">KINTERRUPT_MODE</a> that specifies the interrupt mode associated with the message.  


## -remarks


Miniport drivers retrieve the MSI information in a <b>MESSAGE_INTERRUPT_INFORMATION</b> structure by calling the <a href="..\storport\nf-storport-storportgetmsiinfo.md">StorPortGetMSIInfo</a> routine. 



## -see-also

<a href="..\storport\nf-storport-storportgetmsiinfo.md">StorPortGetMSIInfo</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20MESSAGE_INTERRUPT_INFORMATION structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

