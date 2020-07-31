---
UID: NF:wiamindr_lh.IWiaMiniDrv.drvGetDeviceErrorStr
title: IWiaMiniDrv::drvGetDeviceErrorStr (wiamindr_lh.h)
description: The IWiaMiniDrv::drvGetDeviceErrorStr method maps an error code to a Unicode string that describes the error.
old-location: image\iwiaminidrv_drvgetdeviceerrorstr.htm
tech.root: image
ms.assetid: c34a6834-8875-400c-9634-6c2b9b68164f
ms.date: 05/03/2018
keywords: ["IWiaMiniDrv::drvGetDeviceErrorStr"]
ms.keywords: IWiaMiniDrv interface [Imaging Devices],drvGetDeviceErrorStr method, IWiaMiniDrv.drvGetDeviceErrorStr, IWiaMiniDrv::drvGetDeviceErrorStr, MiniDrv_d5a72b62-8987-4d0a-921e-8a7f4d915d12.xml, drvGetDeviceErrorStr, drvGetDeviceErrorStr method [Imaging Devices], drvGetDeviceErrorStr method [Imaging Devices],IWiaMiniDrv interface, image.iwiaminidrv_drvgetdeviceerrorstr, wiamindr_lh/IWiaMiniDrv::drvGetDeviceErrorStr
f1_keywords:
 - "wiamindr_lh/IWiaMiniDrv.drvGetDeviceErrorStr"
 - "IWiaMiniDrv.drvGetDeviceErrorStr"
req.header: wiamindr_lh.h
req.include-header: Wiamindr.h
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- wiamindr_lh.h
api_name:
- IWiaMiniDrv.drvGetDeviceErrorStr
targetos: Windows
req.typenames: 
---

# IWiaMiniDrv::drvGetDeviceErrorStr

## -description

The **IWiaMiniDrv::drvGetDeviceErrorStr **method maps an error code to a Unicode string that describes the error.

## -parameters

### -param __MIDL__IWiaMiniDrv0039

lDevErrVal [in]

- Specifies the device error value to be mapped to a string. A value of zero indicates that no error occurred.

### -param __MIDL__IWiaMiniDrv0040

lFlags [in]

- Is currently unused.

### -param __MIDL__IWiaMiniDrv0041

plDevErr [out]

- Points to a memory location that will receive a status code for this method. If this method returns S_OK, the value stored will be zero. Otherwise, a minidriver-specific error code will be stored at the location pointed to by this parameter.

### -param __MIDL__IWiaMiniDrv0042

ppszDevErrStr [out, optional]

- Points to a memory location that will receive the address of a string describing the error.

#### - lDevErrVal [in]

Specifies the device error value to be mapped to a string. A value of zero indicates that no error occurred.

#### - lFlags [in]

Is currently unused.

#### - plDevErr [out]

Points to a memory location that will receive a status code for this method. If this method returns S_OK, the value stored will be zero. Otherwise, a minidriver-specific error code will be stored at the location pointed to by this parameter.

#### - ppszDevErrStr [out, optional]

Points to a memory location that will receive the address of a string describing the error.

## -returns

On success, the method should return S_OK and clear the device error value pointed to by *plDevErr*. If the minidriver does not fully implement this method, the method should return E_NOTIMPL. If the minidriver does not recognize the error value passed to this method, the method should return E_INVALIDARG. If the method fails, it should return a standard COM error code and place a minidriver-specific error code value in the memory pointed to by *plDevErr*.

## -remarks

To obtain an error string that describes a device-specific minidriver-generated error value, the WIA service calls the **IWiaMiniDrv::drvGetDeviceErrorStr** method. In response to this call, the minidriver should use [**CoTaskMemAlloc**](https://docs.microsoft.com/windows/win32/api/combaseapi/nf-combaseapi-cotaskmemalloc) to allocate memory that will contain a localized Unicode string corresponding to the error code passed to the minidriver. The WIA service (or an application) will free the memory. It is likely that an application will display the string, so it should be meaningful to an end user. The string should be loaded from a resource file, so that it can be localized into a variety of languages.
