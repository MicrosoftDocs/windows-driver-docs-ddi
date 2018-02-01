---
UID: NF:stiusd.IStiUSD.Initialize
title: IStiUSD::Initialize method
author: windows-driver-content
description: A still image minidriver's IStiUSD::Initialize method initializes an instance of the COM object that defines the IStiUSD interface.
old-location: image\istiusd_initialize.htm
old-project: image
ms.assetid: a2aa0ce6-f63b-4df4-b1c4-a23e80cdcd6c
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: Initialize method [Imaging Devices], image.istiusd_initialize, stifnc_b587b574-dd44-47a2-9d04-78e34733a456.xml, IStiUSD, Initialize method [Imaging Devices], IStiUSD interface, IStiUSD interface [Imaging Devices], Initialize method, stiusd/IStiUSD::Initialize, Initialize, IStiUSD::Initialize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: stiusd.h
req.include-header: Stiusd.h
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
req.lib: stiusd.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	stiusd.h
apiname:
-	IStiUSD.Initialize
product: Windows
targetos: Windows
req.typenames: STI_WIA_DEVICE_INFORMATIONW, *PSTI_WIA_DEVICE_INFORMATIONW
req.product: Windows 10 or later.
---

# IStiUSD::Initialize method


## -description


A still image minidriver's <b>IStiUSD::Initialize</b> method initializes an instance of the COM object that defines the <b>IStiUSD</b> interface.


## -syntax


````
HRESULT Initialize(
   PSTIDEVICECONTROL pDcb,
   DWORD             dwStiVersion,
   HKEY              hParametersKey
);
````


## -parameters




### -param pHelDcb




### -param dwStiVersion

Caller-supplied STI version number. This value is defined by STI_VERSION in <i>Sti.h</i>.


### -param hParametersKey

Caller-supplied handle to the registry key under which device-specific information is to be stored.


#### - pDcb

Caller-supplied pointer to the <a href="https://msdn.microsoft.com/6d98f5d7-c471-4abb-8e69-dbac3d336c2f">IStiDeviceControl COM Interface</a>.


## -returns


If the operation succeeds, the method should return S_OK. Otherwise, it should return one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.



## -remarks


The <b>IStiUSD::Initialize</b> method, which is exported by still image minidrivers, is the first <b>IStiUSD</b> method called after a minidriver has been loaded. The method must initialize the driver and device.

The method should store the received <a href="https://msdn.microsoft.com/6d98f5d7-c471-4abb-8e69-dbac3d336c2f">IStiDeviceControl COM Interface</a> pointer, and it should call that interface's <a href="https://msdn.microsoft.com/library/windows/hardware/ff542933">IStiDeviceControl::AddRef</a> method.

For devices connected to dedicated ports (such as SCSI devices), the method typically creates a read/write path to the device by calling <a href="https://msdn.microsoft.com/80a96083-4de9-4422-9705-b8ad2b6cbd1b">CreateFile</a> (described in the Microsoft Windows SDK documentation), using a device port name obtained by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff542944">IStiDeviceControl::GetMyDevicePortName</a>.

For devices on shared ports (such as serial port devices), opening the port in the <b>IStiUSD::Initialize</b> method is not recommended, because access to other devices on the port will be locked out. For such devices, it is better to call <a href="https://msdn.microsoft.com/80a96083-4de9-4422-9705-b8ad2b6cbd1b">CreateFile</a> from within the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543829">IStiUSD::LockDevice</a> method.

 If the device being opened is one for which multiple calls to <a href="https://msdn.microsoft.com/80a96083-4de9-4422-9705-b8ad2b6cbd1b">CreateFile</a> are not allowed (such as devices connected to a serial port), the driver typically does not call <b>CreateFile</b> unless the caller has opened the device for data transfers, as illustrated in the following <b>CodeExample</b>.

The <b>IStiUSD::Initialize</b> method should validate the received STI version number and return an error if the received version does not match the driver's version.

The following example opens a device port only if a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff542942">IStiDeviceControl::GetMyDeviceOpenMode</a> indicates an application has opened the device for data transfers. Such code might be used for a device that cannot support multiple <a href="https://msdn.microsoft.com/80a96083-4de9-4422-9705-b8ad2b6cbd1b">CreateFile</a> calls, such as a serial port device.


