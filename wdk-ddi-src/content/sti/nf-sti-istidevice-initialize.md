---
UID: NF:sti.IStiDevice.Initialize
title: IStiDevice::Initialize method
author: windows-driver-content
description: The IStiDevice::Initialize method initializes an instance of the COM object that defines the IStiDevice interface. This method is for internal use only.
old-location: image\istidevice_initialize.htm
old-project: image
ms.assetid: 3cd6ece6-2c8e-4072-8ac5-d1e90c9392db
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: IStiDevice::Initialize, Initialize method [Imaging Devices], IStiDevice interface, Initialize, stifnc_abeacac4-60ef-41f0-b70e-bf7da7fa110b.xml, IStiDevice, image.istidevice_initialize, IStiDevice interface [Imaging Devices], Initialize method, sti/IStiDevice::Initialize, Initialize method [Imaging Devices]
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
req.lib: sti.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	sti.h
apiname:
-	IStiDevice.Initialize
product: Windows
targetos: Windows
req.typenames: STI_DEVICE_MJ_TYPE
req.product: Windows 10 or later.
---

# IStiDevice::Initialize method


## -description


The <b>IStiDevice::Initialize</b> method initializes an instance of the COM object that defines the <b>IStiDevice</b> interface. <i>This method is for internal use only</i>.


## -syntax


````
HRESULT Initialize(
  [in] HINSTANCE hinst,
  [in] LPCWSTR   pwszDeviceName,
       DWORD     dwVersion,
       DWORD     dwMode
);
````


## -parameters




### -param hinst [in]

Caller-supplied instance handle of the calling process. This handle is obtained by calling <b>GetModuleName</b>(NULL).


### -param pwszDeviceName [in]

Caller-supplied pointer to a string representing an internal device name, obtained by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff543790">IStillImage::GetSTILaunchInformation</a>.


### -param dwVersion

Caller-supplied STI version number. This value must be STI_VERSION, defined in <i>Sti.h</i>.


### -param dwMode

Caller-supplied constant value indicating the <a href="https://msdn.microsoft.com/79af0d8f-dd04-4ff4-a047-f415562a16a5">Transfer Modes</a> in which the device is to be used. The following values are valid.
<table>
<tr>
<th>Mode</th>
<th>Description</th>
</tr>
<tr>
<td>
STI_DEVICE_CREATE_BOTH

</td>
<td>
The device is being opened for both obtaining status and transferring data.

</td>
</tr>
<tr>
<td>
STI_DEVICE_CREATE_DATA

</td>
<td>
The device is being opened only for data transfers.

</td>
</tr>
<tr>
<td>
STI_DEVICE_CREATE_STATUS

</td>
<td>
The device is being opened only for obtaining status information.

</td>
</tr>
</table> 


## -returns


If the operation succeeds, the method returns S_OK. Otherwise, it returns one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.



## -remarks


The <b>IStiDevice::Initialize</b> method initializes the COM object instance that was created by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff543778">IStillImage::CreateDevice</a>.

Because <b>IStiDevice::Initialize</b> is called by <b>IStillImage::CreateDevice</b>, clients of the <b>IStiDevice</b> interface do not typically call this method directly.


