---
UID: NF:sti.IStillImageW.SetDeviceValue
title: IStillImageW::SetDeviceValue
author: windows-driver-content
description: The IStillImage::SetDeviceValue method sets registry information for a specified still image device.
old-location: image\istillimage_setdevicevalue.htm
old-project: image
ms.assetid: e2ea9c59-cc63-4ced-a225-e0c9667dd574
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: IStillImageW interface [Imaging Devices],SetDeviceValue method, IStillImageW.SetDeviceValue, IStillImageW::SetDeviceValue, SetDeviceValue, SetDeviceValue method [Imaging Devices], SetDeviceValue method [Imaging Devices],IStillImageW interface, image.istillimage_setdevicevalue, sti/IStillImageW::SetDeviceValue, stifnc_74822300-cad0-43db-80b9-d3f868afcd19.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: sti.h
req.include-header: Sti.h
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	sti.h
api_name:
-	IStillImageW.SetDeviceValue
product: Windows
targetos: Windows
req.typenames: 
---

# IStillImageW::SetDeviceValue


## -description


The <b>IStillImage::SetDeviceValue</b> method sets registry information for a specified still image device.


## -parameters




### -param pwszDeviceName [in]

Caller-supplied pointer to a string representing an internal device name, obtained by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff543790">IStillImage::GetSTILaunchInformation</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff543784">IStillImage::GetDeviceList</a>.


### -param pValueName [in]

Caller-supplied pointer to a string representing a registry value name.


### -param Type

Caller-supplied REG_-prefixed registry value type. For more information, see <b>RegSetValueEx</b> in the Microsoft Windows SDK documentation.


### -param pData [in]

Caller-supplied pointer to the data to be stored.


### -param cbData

Caller-supplied size, in bytes, of the data pointed to by <i>pData</i>. For NULL-terminated strings, include the NULL character.


## -returns



If the operation succeeds, the method returns S_OK. Otherwise, it returns one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.




## -remarks



The purpose of the <b>IStillImage::SetDeviceValue</b> method is to set values for device-specific <a href="https://msdn.microsoft.com/cedc8afc-54c4-485e-989c-481fe30d899b">Registry Entries for Still Image Devices</a>. The method calls <b>RegSetValueEx</b> (described in the Microsoft Windows SDK documentation).

Before calling <b>IStillImage::SetDeviceValue</b>, clients of the <b>IStillImage</b> COM interface must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff543804">IStillImage::StiCreateInstance</a> to obtain an <b>IStillImage</b> interface pointer.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543786">IStillImage::GetDeviceValue</a>



<a href="https://msdn.microsoft.com/a9ceee48-cbb5-4448-83b4-9c19fe89fcb9">IStillImageW</a>
 

 

