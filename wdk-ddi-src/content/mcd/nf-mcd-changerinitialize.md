---
UID: NF:mcd.ChangerInitialize
title: ChangerInitialize function
author: windows-driver-content
description: ChangerInitialize readies the changer to receive other requests.
old-location: storage\changerinitialize.htm
old-project: storage
ms.assetid: 7cb90d35-53e5-4c73-a1f5-9fc3f99cf1b2
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: ChangerInitialize, ChangerInitialize function [Storage Devices], chgrmini_025ae048-8625-4039-82a2-29d99dcc4972.xml, mcd/ChangerInitialize, storage.changerinitialize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: mcd.h
req.include-header: Mcd.h, Ntddchgr.h
req.target-type: Desktop
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	mcd.h
api_name:
-	ChangerInitialize
product: Windows
targetos: Windows
req.typenames: LAMP_INTENSITY_WHITE
---

# ChangerInitialize function


## -description


<b>ChangerInitialize</b> readies the changer to receive other requests. 


## -syntax


````
NTSTATUS ChangerInitialize(
  _In_ PDEVICE_OBJECT DeviceObject
);
````


## -parameters




### -param DeviceObject [in]

Pointer to the device object created by the changer class driver to represent this changer. 


## -returns



<b>ChangerInitialize</b> returns the STATUS_<i>XXX</i> value returned by the system port driver or one of the following values:
      

STATUS_SUCCESS

STATUS_INSUFFICIENT_RESOURCES




## -remarks



The changer class driver calls <b>ChangerInitialize</b> during driver initialization, after creating a device object to represent a changer. 

<b>ChangerInitialize</b> performs any device-specific processing required to get the changer ready to receive requests. It also typically stores device-specific information in the device extension, such as SCSI inquiry data or the non-SCSI equivalent and offsets to generate zero-based element addresses, which are used by the system to refer to changer elements.

After <b>ChangerInitialize</b> returns, the changer miniclass driver and the changer should be able to handle any other request. 




## -see-also

<a href="..\mcd\nf-mcd-changeradditionalextensionsize.md">ChangerAdditionalExtensionSize</a>



 

 


