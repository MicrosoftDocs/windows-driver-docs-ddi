---
UID: NN:wia_lh.IWiaLog
title: IWiaLog (wia_lh.h)
description: The IWiaLog interface provides methods to enable minidrivers to log trace, error, and warning messages to the diagnostic log file Wiaservc.log.
old-location: image\iwialog_interface.htm
tech.root: image
ms.assetid: b56cb3f0-1053-4104-b223-e7448a832f33
ms.date: 05/03/2018
ms.keywords: IWiaLog, IWiaLog interface [Imaging Devices], IWiaLog interface [Imaging Devices],described, IWiaLog_0284e394-6bc5-40b8-8174-0041bfc0d5dd.xml, image.iwialog_interface, wia_lh/IWiaLog
ms.topic: interface
f1_keywords:
 - "wia_lh/IWiaLog"
req.header: wia_lh.h
req.include-header: 
req.target-type: Windows
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
- wia_lh.h
api_name:
- IWiaLog
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWiaLog interface

## -description

> [!IMPORTANT]
> The IWiaLog interface is obsolete and is no longer supported. Instead, use the [Diagnostic Log Macros](https://docs.microsoft.com/windows-hardware/drivers/image/wia-diagnostic-log-macros).

The **IWiaLog** interface provides methods to enable minidrivers to log trace, error, and warning messages to the diagnostic log file Wiaservc.log. 

The prototypes for the methods appear in *Wia.h*. The diagnostic log file *Wiaservc.log* is found in the Windows directory, or in the directory returned by the [GetWindowsDirectory](https://docs.microsoft.com/windows/win32/api/sysinfoapi/nf-sysinfoapi-getwindowsdirectorya) system API call.

## -inheritance

The **IWiaLog** interface inherits from the [IUnknown](https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown) interface. **IWiaLog** also has these types of members:

- **Methods**

