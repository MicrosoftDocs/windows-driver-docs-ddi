---
UID: NF:wdfdevice.WdfDeviceSetSpecialFileSupport
title: WdfDeviceSetSpecialFileSupport function (wdfdevice.h)
description: The WdfDeviceSetSpecialFileSupport method enables or disables a function driver's support for special files, for the specified device.
old-location: wdf\wdfdevicesetspecialfilesupport.htm
tech.root: wdf
ms.assetid: 7648c486-181a-45c8-9c4b-e3158428046a
ms.date: 02/26/2018
keywords: ["WdfDeviceSetSpecialFileSupport function"]
ms.keywords: DFDeviceObjectGeneralRef_c40463ef-3c26-431e-99d8-d176b0ef7ebf.xml, WdfDeviceSetSpecialFileSupport, WdfDeviceSetSpecialFileSupport method, kmdf.wdfdevicesetspecialfilesupport, wdf.wdfdevicesetspecialfilesupport, wdfdevice/WdfDeviceSetSpecialFileSupport
f1_keywords:
 - "wdfdevice/WdfDeviceSetSpecialFileSupport"
 - "WdfDeviceSetSpecialFileSupport"
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: <=DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
api_name:
- WdfDeviceSetSpecialFileSupport
targetos: Windows
req.typenames: 
---

# WdfDeviceSetSpecialFileSupport function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfDeviceSetSpecialFileSupport</b> method enables or disables a function driver's support for special files, for the specified device.


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param FileType [in]

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ne-wdfdevice-_wdf_special_file_type">WDF_SPECIAL_FILE_TYPE</a>-typed enumerator that identifies the type of special file that the driver supports.


### -param FileTypeIsSupported [in]

Supplies a Boolean value which, if <b>TRUE</b>, enables support for the special file type and, if <b>FALSE</b>, disables support the special file type.


## -remarks

A bug check occurs if the driver supplies an invalid object handle.




A function driver typically calls <b>WdfDeviceSetSpecialFileSupport</b> from within its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a> callback function.

Each driver's support for special files is initially disabled until the driver calls <b>WdfDeviceSetSpecialFileSupport</b>.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/supporting-special-files">Supporting Special Files</a>.


#### Examples

The following code example enables support for paging, hibernation, and dump files on a device.

```cpp
WdfDeviceSetSpecialFileSupport(
                               device,
                               WdfSpecialFilePaging,
                               TRUE
                               );
WdfDeviceSetSpecialFileSupport(
                               device,
                               WdfSpecialFileHibernation,
                               TRUE
                               );
WdfDeviceSetSpecialFileSupport(
                               device,
                               WdfSpecialFileDump,
                               TRUE
                               );
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ne-wdfdevice-_wdf_special_file_type">WDF_SPECIAL_FILE_TYPE</a>
 

 

