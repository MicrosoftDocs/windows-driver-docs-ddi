---
UID: NF:ks.IKsControl.KsProperty
title: IKsControl::KsProperty
author: windows-driver-content
description: The IKsControl::KsProperty method sets a property or retrieves property information, together with any other defined support operations available on a property set.
old-location: stream\ikscontrol_ksproperty2.htm
old-project: stream
ms.assetid: a80312ef-394a-4a59-8a04-35d7c60689b6
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: IKsControl interface [Streaming Media Devices],KsProperty method, IKsControl.KsProperty, IKsControl::KsProperty, KsProperty, KsProperty method [Streaming Media Devices], KsProperty method [Streaming Media Devices],IKsControl interface, avintfc_100fad0d-8ca1-4cf1-88b0-e6ec1a3c55fe.xml, ks/IKsControl::KsProperty, stream.ikscontrol_ksproperty2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: ks.h
req.include-header: Ks.h
req.target-type: DesktopMobile
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
-	COM
api_location:
-	ks.h
api_name:
-	IKsControl.KsProperty
product:
- Windows
targetos: Windows
req.typenames: 
---

# IKsControl::KsProperty


## -description


The <b>IKsControl::KsProperty</b> method sets a property or retrieves property information, together with any other defined support operations available on a property set. 


## -parameters




### -param Property [in]

Pointer to a structure that describes a property and the request type of the property request. This structure must be either a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a> or a structure that contains a <b>KSPROPERTY</b> structure as its first member. An example of a structure that can be pointed to by this member is the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566089">KSPROPERTY_VIDEOPROCAMP_S</a> structure.


### -param PropertyLength [in]

Specifies size, in bytes, of the buffer at <i>Property</i>.


### -param PropertyData [in, out]

Pointer to a buffer that contains data for a KSPROPERTY_TYPE_SET, KSPROPERTY_TYPE_UNSERIALIZESET, or KSPROPERTY_TYPE_UNSERIALIZERAW operation, or buffer space that receives data for all other operations.


### -param DataLength [in]

Specifies size, in bytes, of the buffer at <i>PropertyData</i>.


### -param BytesReturned [out]

Pointer to a variable that receives the size, in bytes, of the data that <b>KsProperty</b> stores in the buffer at <i>PropertyData</i>. If no data is stored, the size is zero.


## -returns



The <b>IKsControl::KsProperty</b> method returns the same value that would be returned if the property had been sent by IOCTL.




## -remarks



To determine the buffer size that is required for a specific property request, you can call this method with <i>PropertyData</i> set to <b>NULL</b> and <i>DataLength</i> equal to zero. The method returns HRESULT_FROM_WIN32(ERROR_MORE_DATA), and <i>BytesReturned</i> contains the size of the required buffer.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565176">KSPROPERTY_ITEM</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565617">KSPROPERTY_SET</a>
 

 

