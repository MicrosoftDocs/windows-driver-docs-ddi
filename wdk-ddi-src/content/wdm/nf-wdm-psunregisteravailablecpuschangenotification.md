---
UID: NF:wdm.PsUnregisterAvailableCpusChangeNotification
tech.root: kernel
title: PsUnregisterAvailableCpusChangeNotification
ms.date: 08/05/2025
targetos: Windows
description: The PsUnregisterAvailableCpusChangeNotification function unregisters a registration previously performed by PsRegisterProcessAvailableCpusChangeNotification or PsRegisterSystemAvailableCpusChangeNotification.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.idl: 
req.include-header: 
req.irql: PASSIVE_LEVEL
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
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - PsUnregisterAvailableCpusChangeNotification
f1_keywords:
 - PsUnregisterAvailableCpusChangeNotification
 - wdm/PsUnregisterAvailableCpusChangeNotification
dev_langs:
 - c++
helpviewer_keywords:
 - PsUnregisterAvailableCpusChangeNotification
---

## -description

The **PsUnregisterAvailableCpusChangeNotification** function unregisters a registration previously performed by [**PsRegisterProcessAvailableCpusChangeNotification**](nf-wdm-psregisterprocessavailablecpuschangenotification.md) or [**PsRegisterSystemAvailableCpusChangeNotification**](nf-wdm-psregistersystemavailablecpuschangenotification.md).

## -parameters

### -param RegistrationHandle [in]

Handle returned by a call to [**PsRegisterProcessAvailableCpusChangeNotification**](nf-wdm-psregisterprocessavailablecpuschangenotification.md) or [**PsRegisterSystemAvailableCpusChangeNotification**](nf-wdm-psregistersystemavailablecpuschangenotification.md).

## -remarks

This routine must be called at PASSIVE_LEVEL.

After this function returns, the callback associated with the registration handle will no longer be invoked for CPU availability changes.

This function can be used to unregister callbacks registered for both process-specific and system-wide CPU availability change notifications.

## -see-also

[**PsRegisterProcessAvailableCpusChangeNotification**](nf-wdm-psregisterprocessavailablecpuschangenotification.md)

[**PsRegisterSystemAvailableCpusChangeNotification**](nf-wdm-psregistersystemavailablecpuschangenotification.md)
