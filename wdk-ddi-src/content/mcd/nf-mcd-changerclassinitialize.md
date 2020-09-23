---
UID: NF:mcd.ChangerClassInitialize
title: ChangerClassInitialize function (mcd.h)
description: The ChangerClassInitialize routine initializes the driver.
old-location: storage\changerclassinitialize.htm
tech.root: storage
ms.assetid: b19f85f7-fe51-4539-8c36-e3c6a299faad
ms.date: 03/29/2018
keywords: ["ChangerClassInitialize function"]
ms.keywords: ChangerClassInitialize, ChangerClassInitialize routine [Storage Devices], chgrclas_f0aa8547-be16-44aa-bd15-a4828d7f57f5.xml, mcd/ChangerClassInitialize, storage.changerclassinitialize
req.header: mcd.h
req.include-header: Mcd.h, Ntddchgr.h
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
req.lib: Mcd.lib
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - ChangerClassInitialize
 - mcd/ChangerClassInitialize
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Mcd.lib
 - Mcd.dll
api_name:
 - ChangerClassInitialize
---

# ChangerClassInitialize function


## -description

The <b>ChangerClassInitialize</b> routine initializes the driver.

## -parameters

### -param DriverObject 

[in]
Pointer to the changer miniclass driver object.  This is passed as a parameter to the miniclass driver's <b>DriverEntry</b> routine. The format of this object is operating system-specific and should not be interpreted by the miniclass driver.

### -param RegistryPath 

[in]
Pointer to the registry path for changer miniclass driver. This is also passed as a parameter to the miniclass driver's <b>DriverEntry</b> routine. The format of this is operating system-specific and should not be interpreted by the miniclass driver.

### -param ChangerInitData

<p>Pointer to an <a href="/windows-hardware/drivers/ddi/mcd/ns-mcd-_mcd_init_data"><b>MCD_INIT_DATA</b></a> structure containing miniclass driver-specific information such as the entry points for the changer miniclass driver's command processing routines. </p>

## -returns

<b>ChangerClassInitialize</b> returns a value indicating the success or failure of  the driver initialization. If initialization is successful, <b>ChangerClassInitialize</b> returns STATUS_SUCCESS. Otherwise, <b>ChangerClassInitialize</b> returns an appropriate error message. Minidrivers should <i>not</i> interpret this error value, but should just return this value from their <b>DriverEntry</b> routine.

## -remarks

<b>ChangerClassInitialize</b> is a changer class driver routine that miniclass drivers can call in Microsoft Windows XP and later operating systems.

Changer miniclass drivers call <b>ChangerClassInitialize</b> from within their <b>DriverEntry</b> routines to initialize the driver. <b>ChangerClassInitialize</b> performs many tasks formerly performed by the changer class driver's <b>DriverEntry</b> routine such as registering the miniclass driver's dispatch routines. It allocates a driver object extension and copies the data contained in <i>MCDInitData</i> into the driver object extension along with other initialization data such as the driver's registry path and pointers to certain changer class driver routines that are operating system-specific. 

Changer miniclass drivers must allocate an <a href="/windows-hardware/drivers/ddi/mcd/ns-mcd-_mcd_init_data">MCD_INIT_DATA</a> structure, zero the structure by calling <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlzeromemory">RtlZeroMemory</a>, and then assign values to the appropriate members, before passing the structure's address to <b>ChangerClassInitialize</b> by means of the <i>MCDInitData</i> parameter.

## -see-also

<a href="/windows-hardware/drivers/ddi/mcd/ns-mcd-_mcd_init_data">MCD_INIT_DATA</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlzeromemory">RtlZeroMemory</a>