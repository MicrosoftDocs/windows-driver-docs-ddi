---
UID: NF:sti.StiCreateInstanceW
tech.root: image
title: StiCreateInstanceW
ms.date: 10/06/2022
targetos: Windows
description: Learn more about the IStillImage::StiCreateInstance method.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: sti.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - sti.h
api_name:
 - StiCreateInstanceW
 - StiCreateInstance
f1_keywords:
 - StiCreateInstanceW
 - sti/StiCreateInstanceW
 - StiCreateInstance
 - sti/StiCreateInstance
dev_langs:
 - c++
helpviewer_keywords:
 - StiCreateInstanceW
---

## -description

The **IStillImage::StiCreateInstance** method creates an instance of the COM object that defines the **IStillImage** interface, and returns a pointer to the interface.

## -parameters

### -param hinst

Caller-supplied instance handle of the calling process. This handle is obtained by calling **GetModuleHandle**(**NULL**).

### -param dwVer

Caller-supplied STI version number. This value must be STI\_VERSION, defined in *Sti.h*.

### -param ppSti

Receives a pointer to the **IStillImage** interface.

### -param punkOuter

Optional, caller-supplied pointer to the "controlling unknown" for object aggregation. See the following **Remarks** section.

## -returns

If the operation succeeds, the method returns S\_OK. Otherwise, it returns one of the STIERR-prefixed error codes defined in *stierr.h*.

## -remarks

For an application to use the **IStillImage** interface, it must first call **IStillImage::StiCreateInstance** to get a pointer to the interface. The pointer received in *ppSti* is used subsequently when calling **IStillImage** methods, as illustrated in the following example:

    PSTI pSti = NULL;
    DWORD dwStiTotal = 0;     // total number of STI devices found
    PVOID pStiInfo = NULL;    // STI device info buffer
    HRESULT hres = StiCreateInstance(GetModuleHandle(NULL), STI_VERSION, &pSti, NULL);
    ...
    hhes = pSti->GetDeviceList(0, 0, &dwStiTotal, &pStiInfo);

If you want to create an aggregate COM object that includes **IStillImage**, you must supply a pointer to the "controlling unknown" in *punkOuter*. In most cases you will not be creating an aggregate object, so *punkOuter* should be **NULL**. Object aggregation and the controlling unknown are described in the Microsoft Windows SDK documentation and in the *Component Object Model Specification*.

## -see-also

[**IStillImage::Release**](nf-sti-istillimagew-release.md)
