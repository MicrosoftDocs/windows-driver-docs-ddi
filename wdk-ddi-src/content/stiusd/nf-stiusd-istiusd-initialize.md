---
UID: NF:stiusd.IStiUSD.Initialize
title: IStiUSD::Initialize (stiusd.h)
description: A still image minidriver's IStiUSD::Initialize method initializes an instance of the COM object that defines the IStiUSD interface.
old-location: image\istiusd_initialize.htm
tech.root: image
ms.date: 05/03/2018
keywords: ["IStiUSD::Initialize"]
ms.keywords: IStiUSD interface [Imaging Devices],Initialize method, IStiUSD.Initialize, IStiUSD::Initialize, Initialize, Initialize method [Imaging Devices], Initialize method [Imaging Devices],IStiUSD interface, image.istiusd_initialize, stifnc_b587b574-dd44-47a2-9d04-78e34733a456.xml, stiusd/IStiUSD::Initialize
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - IStiUSD::Initialize
 - stiusd/IStiUSD::Initialize
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - stiusd.h
api_name:
 - IStiUSD::Initialize
---

# IStiUSD::Initialize


## -description

A still image minidriver's **IStiUSD::Initialize** method initializes an instance of the COM object that defines the **IStiUSD** interface.

## -parameters

### -param pHelDcb

### -param dwStiVersion

Caller-supplied STI version number. This value is defined by STI_VERSION in *Sti.h*.

### -param hParametersKey

Caller-supplied handle to the registry key under which device-specific information is to be stored.

#### - pDcb

Caller-supplied pointer to the [IStiDeviceControl COM Interface](/windows-hardware/drivers/image/istidevicecontrol-com-interface).

## -returns

If the operation succeeds, the method should return S_OK. Otherwise, it should return one of the STIERR-prefixed error codes defined in *stierr.h*.

## -remarks

The **IStiUSD::Initialize** method, which is exported by still image minidrivers, is the first **IStiUSD** method called after a minidriver has been loaded. The method must initialize the driver and device.

The method should store the received [IStiDeviceControl COM Interface](/windows-hardware/drivers/image/istidevicecontrol-com-interface) pointer, and it should call that interface's [IStiDeviceControl::AddRef](./nf-stiusd-istidevicecontrol-addref.md) method.

For devices connected to dedicated ports (such as SCSI devices), the method typically creates a read/write path to the device by calling [CreateFile](/windows/win32/api/fileapi/nf-fileapi-createfilea) (described in the Microsoft Windows SDK documentation), using a device port name obtained by calling [IStiDeviceControl::GetMyDevicePortName](./nf-stiusd-istidevicecontrol-getmydeviceportname.md).

For devices on shared ports (such as serial port devices), opening the port in the **IStiUSD::Initialize** method is not recommended, because access to other devices on the port will be locked out. For such devices, it is better to call [CreateFile](/windows/win32/api/fileapi/nf-fileapi-createfilea) from within the [IStiUSD::LockDevice](./nf-stiusd-istiusd-lockdevice.md) method.

 If the device being opened is one for which multiple calls to [CreateFile](/windows/win32/api/fileapi/nf-fileapi-createfilea) are not allowed (such as devices connected to a serial port), the driver typically does not call **CreateFile** unless the caller has opened the device for data transfers, as illustrated in the following **CodeExample**.

The **IStiUSD::Initialize** method should validate the received STI version number and return an error if the received version does not match the driver's version.

The following example opens a device port only if a call to [IStiDeviceControl::GetMyDeviceOpenMode](./nf-stiusd-istidevicecontrol-getmydeviceopenmode.md) indicates an application has opened the device for data transfers. Such code might be used for a device that cannot support multiple [CreateFile](/windows/win32/api/fileapi/nf-fileapi-createfilea) calls, such as a serial port device.

### Examples

```cpp
STDMETHODIMP MyUSDDevice::Initialize(
    PSTIDEVICECONTROL pDcb,
    DWORD             dwStiVersion,
    HKEY              hParametersKey)
{
    HRESULT hres = STI_OK;
    DWORD   dwMode = 0;
    if (!pDcb)
    {
        hres = STIERR_INVALID_PARAM;
    }
    else
    {
        // Store IStiDeviceControl object pointer
        m_pDcb = pDcb;
        m_pDcb->AddRef();
        // If we opened in data mode - should open device right now,
        // otherwise postpone open till lock
        m_pDcb->GetMyDeviceOpenMode(&dwMode);
        if (dwMode & STI_DEVICE_CREATE_DATA)
            hres = OpenMyPort();
    }
    return hres;
}
```

