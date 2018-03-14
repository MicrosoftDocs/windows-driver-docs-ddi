---
UID: NF:sti.IStillImageW.SetDeviceValue
title: IStillImageW::SetDeviceValue method
author: windows-driver-content
description: The IStillImage::SetDeviceValue method sets registry information for a specified still image device.
old-location: image\istillimage_setdevicevalue.htm
old-project: image
ms.assetid: e2ea9c59-cc63-4ced-a225-e0c9667dd574
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: IStillImageW, IStillImageW interface [Imaging Devices], SetDeviceValue method, IStillImageW::SetDeviceValue, SetDeviceValue method [Imaging Devices], SetDeviceValue method [Imaging Devices], IStillImageW interface, SetDeviceValue,IStillImageW.SetDeviceValue, image.istillimage_setdevicevalue, sti/IStillImageW::SetDeviceValue, stifnc_74822300-cad0-43db-80b9-d3f868afcd19.xml
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
req.typenames: STI_DEVICE_MJ_TYPE, STI_DEVICE_MJ_TYPE
req.product: Windows 10 or later.
---

# IStillImageW::SetDeviceValue method


## -description


The <b>IStillImage::SetDeviceValue</b> method sets registry information for a specified still image device.


## -syntax


````
HRESULT SetDeviceValue(
  [in] LPWSTR pwszDeviceName,
  [in] LPWSTR pValueName,
       DWORD  Type,
  [in] LPBYTE pData,
       DWORD  cbData
);
````


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

<a href="https://msdn.microsoft.com/a9ceee48-cbb5-4448-83b4-9c19fe89fcb9">IStillImageW</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543786">IStillImage::GetDeviceValue</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20IStillImageW::SetDeviceValue method%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

