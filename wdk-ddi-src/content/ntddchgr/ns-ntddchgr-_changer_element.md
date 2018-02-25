---
UID: NS:ntddchgr._CHANGER_ELEMENT
title: "_CHANGER_ELEMENT"
author: windows-driver-content
description: The CHANGER_ELEMENT structure contains a description of a changer element.
old-location: storage\changer_element.htm
old-project: storage
ms.assetid: 85035147-0ae8-482a-9a12-1e4e53ae1969
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *PCHANGER_ELEMENT, ,, A, C, CHANGER_ELEMENT, CHANGER_ELEMENT structure [Storage Devices], E, G, H, L, M, N, P, PCHANGER_ELEMENT, PCHANGER_ELEMENT structure pointer [Storage Devices], R, T, _, _CHANGER_ELEMENT, ntddchgr/CHANGER_ELEMENT, ntddchgr/PCHANGER_ELEMENT, storage.changer_element, structs-changer_b1685d99-20ff-495d-a9e3-c63571559106.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddchgr.h
req.include-header: 
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
-	ntddchgr.h
apiname:
-	CHANGER_ELEMENT
product: Windows
targetos: Windows
req.typenames: CHANGER_ELEMENT, *PCHANGER_ELEMENT
---

# _CHANGER_ELEMENT structure


## -description


The CHANGER_ELEMENT structure contains a description of a changer element. 


## -syntax


````
typedef struct _CHANGER_ELEMENT {
  ELEMENT_TYPE ElementType;
  ULONG        ElementAddress;
} CHANGER_ELEMENT, *PCHANGER_ELEMENT;
````


## -struct-fields




### -field ElementType

Indicates the type of element. Can be one of the following values taken from the <a href="..\ntddchgr\ne-ntddchgr-_element_type.md">ELEMENT_TYPE</a> enumeration.





#### AllElements

All elements of a changer, including its robotic transport, drives, slots, and IEport. <b>AllElements</b> is valid only in a <b>ChangerGetElementStatus</b> or <b>ChangerInitializeElementStatus</b> call.





#### ChangerTransport

The changer's robotic transport element, which is used to move media between IEports, slots, and drives.





#### ChangerSlot

A storage element, which is a slot in the changer in which media is stored when not mounted in a drive.





#### ChangerIEPort

An import/export element (IEport), which is a single or multiple-cartridge access port in some changers. An element is an IEport only if it is possible to move a piece of media from a slot to the IEport.





#### ChangerDrive

A data transfer element where data can be read from and written to media. 





#### ChangerDoor

A mechanism that provides access to all media in a changer at one time (as compared to an IEport that provides access to one or more, but not all, media). For example, a large front door or a magazine that contains all media in the changer are elements of this type. <b>ChangerDoor</b> is valid only in a <b>ChangerSetAccess</b> call.





#### ChangerKeypad

The keypad or other input control on the front panel of a changer. <b>ChangerKeypad</b> is valid only in a <b>ChangerSetAccess</b> call.


### -field ElementAddress

Indicates the element's zero-based address used by the system. A changer miniclass driver is responsible for translating this address to the device-specific address used by the changer.


## -remarks



CHANGER_ELEMENT is used by both the changer class driver and a changer miniclass driver to describe a changer element. 

On input, a changer miniclass driver must translate the zero-based address in <b>ElementAddress</b> to a device-specific address before accessing the element. On output, the driver must translate a device-specific address to the zero-based equivalent before filling in <b>ElementAddress</b>.




## -see-also

<a href="..\ntddchgr\ns-ntddchgr-_changer_element_list.md">CHANGER_ELEMENT_LIST</a>



<a href="..\ntddchgr\ns-ntddchgr-_changer_element_status.md">CHANGER_ELEMENT_STATUS</a>



<a href="..\ntddchgr\ne-ntddchgr-_element_type.md">ELEMENT_TYPE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20CHANGER_ELEMENT structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

