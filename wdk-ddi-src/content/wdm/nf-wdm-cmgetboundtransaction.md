---
UID: NF:wdm.CmGetBoundTransaction
title: CmGetBoundTransaction function (wdm.h)
description: The CmGetBoundTransaction routine returns a pointer to the transaction object that represents the transaction, if any, that is associated with a specified registry key object.
old-location: kernel\cmgetboundtransaction.htm
tech.root: kernel
ms.assetid: f38a5ad6-6816-4b27-98ea-51ac1453d90f
ms.date: 04/30/2018
keywords: ["CmGetBoundTransaction function"]
ms.keywords: CmGetBoundTransaction, CmGetBoundTransaction routine [Kernel-Mode Driver Architecture], ConfigMgrRef_bf8b79d4-04cf-4cd2-b25c-4e59c63f0b86.xml, kernel.cmgetboundtransaction, wdm/CmGetBoundTransaction
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of Windows.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - CmGetBoundTransaction
 - wdm/CmGetBoundTransaction
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - CmGetBoundTransaction
---

# CmGetBoundTransaction function


## -description

The <b>CmGetBoundTransaction</b> routine returns a pointer to the transaction object that represents the <a href="/windows-hardware/drivers/kernel/using-kernel-transaction-manager">transaction</a>, if any, that is associated with a specified registry key object.

## -parameters

### -param Cookie 

[in]
The cookie value that the driver previously obtain by calling <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-cmregistercallback">CmRegisterCallback</a> or <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-cmregistercallbackex">CmRegisterCallbackEx</a>.

### -param Object 

[in]
The pointer value that the driver's <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-ex_callback_function">RegistryCallback</a> callback routine received in one of the <b>REG_<i>XXX</i>_KEY_INFORMATION</b> structures.

## -returns

<b>CmGetBoundTransaction</b> returns a pointer to a transaction object, if the key object that the <i>Object</i> parameter specifies is associated with a transaction. Otherwise, the routine returns <b>NULL</b>.

## -remarks

The <b>CmGetBoundTransaction</b> routine is available on Windows Vista and later versions of Windows.

For more information about <b>CmGetBoundTransaction</b> and filtering registry operations, see <a href="/windows-hardware/drivers/kernel/filtering-registry-calls">Filtering Registry Calls</a>.

For more information about transactions, see <a href="/windows-hardware/drivers/kernel/using-kernel-transaction-manager">Kernel Transaction Manager Design Guide</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-cmregistercallback">CmRegisterCallback</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-cmregistercallbackex">CmRegisterCallbackEx</a>



<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-ex_callback_function">RegistryCallback</a>