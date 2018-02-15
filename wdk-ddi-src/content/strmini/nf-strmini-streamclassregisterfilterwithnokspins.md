---
UID: NF:strmini.StreamClassRegisterFilterWithNoKSPins
title: StreamClassRegisterFilterWithNoKSPins function
author: windows-driver-content
description: The StreamClassRegisterFilterWithNoKSPins routine is used to register filter drivers with Microsoft DirectShow that have no kernel streaming pins and, therefore, do not stream in kernel mode.
old-location: stream\streamclassregisterfilterwithnokspins.htm
old-project: stream
ms.assetid: f5ae426a-9d9d-4391-b87f-c4281dc9cadc
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: StreamClassRegisterFilterWithNoKSPins, strmini/StreamClassRegisterFilterWithNoKSPins, stream.streamclassregisterfilterwithnokspins, strclass-routines_d338a3be-7760-46b6-aeba-e9cbac45afe3.xml, StreamClassRegisterFilterWithNoKSPins routine [Streaming Media Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: strmini.h
req.include-header: Strmini.h
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
req.lib: Stream.lib
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Stream.lib
-	Stream.dll
apiname:
-	StreamClassRegisterFilterWithNoKSPins
product: Windows
targetos: Windows
req.typenames: STREAM_PRIORITY, *PSTREAM_PRIORITY
req.product: Windows 10 or later.
---

# StreamClassRegisterFilterWithNoKSPins function


## -description


The <b>StreamClassRegisterFilterWithNoKSPins</b> routine is used to register filter drivers with Microsoft DirectShow that have no kernel streaming pins and, therefore, do not stream in kernel mode. 


## -syntax


````
NTSTATUS StreamClassRegisterFilterWithNoKSPins(
  _In_           PDEVICE_OBJECT DeviceObject,
  _In_     const GUID           *InterfaceClassGUID,
  _In_           ULONG          PinCount,
  _In_           BOOL           *PinDirection,
  _In_           KSPIN_MEDIUM   *MediumList,
  _In_opt_       GUID           *CategoryList
);
````


## -parameters




### -param DeviceObject [in]

Points to the driver's device object.


### -param InterfaceClassGUID [in]

Specifies the interface class GUID to register.


### -param PinCount [in]

Specifies the number of pins on the filter.


### -param PinDirection [in]

Specifies a <i>PinCount</i>-sized array of Boolean values, one for each pin on the filter. The values indicate the pin direction for each pin. If <b>TRUE</b>, this pin is an output pin. If <b>FALSE</b>, the pin is an input pin.


### -param MediumList [in]

Specifies a <i>PinCount</i>-sized array of <a href="..\ks\ns-ks-ksidentifier.md">KSPIN_MEDIUM</a> structures, one for each pin on the filter.


### -param CategoryList [in, optional]

If non-NULL, specifies an array of pin category GUIDs, one for each pin on the filter.


## -returns



Returns STATUS_SUCCESS on success, or the appropriate error code on failure.




## -see-also

<a href="..\ks\ns-ks-ksidentifier.md">KSPIN_MEDIUM</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20StreamClassRegisterFilterWithNoKSPins routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

