---
UID: NS:sercx._SERCX_CONFIG
title: _SERCX_CONFIG (sercx.h)
description: The SERCX_CONFIG structure contains configuration information for the serial framework extension (SerCx).
old-location: serports\sercx_config.htm
tech.root: serports
ms.assetid: 2CBCBA07-C489-4475-A856-8748FBFDC141
ms.date: 04/23/2018
ms.keywords: "*PSERCX_CONFIG, 1/PSERCX_CONFIG, 1/SERCX_CONFIG, PSERCX_CONFIG, PSERCX_CONFIG structure pointer [Serial Ports], SERCX_CONFIG, SERCX_CONFIG structure [Serial Ports], _SERCX_CONFIG, serports.sercx_config"
ms.topic: struct
f1_keywords:
 - "sercx/SERCX_CONFIG"
req.header: sercx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 8.
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
- HeaderDef
api_location:
- 1.0\Sercx.h
api_name:
- SERCX_CONFIG
product:
- Windows
targetos: Windows
req.typenames: SERCX_CONFIG, *PSERCX_CONFIG
---

# _SERCX_CONFIG structure


## -description


The <b>SERCX_CONFIG</b> structure contains configuration information for the serial framework extension (SerCx).


## -struct-fields




### -field Size

The size, in bytes, of this structure. The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nf-sercx-sercxinitialize">SerCxInitialize</a> method uses this member to determine which version of the structure the caller is using. The size of this structure might change in future versions of the Sercx.h header file.


### -field PowerManaged

Whether the controller queue should be power-managed. If set to <b>WdfTrue</b>, the controller queue should be power-managed.  If set to <b>WdfFalse</b>, the controller queue not be power-managed. If set to <b>WdfDefault</b>, the controller queue should be power-managed unless the driver calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdffdo/nf-wdffdo-wdffdoinitsetfilter">WdfFdoInitSetFilter</a> method. For more information, see the description of the <b>PowerManaged</b> member in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfio/ns-wdfio-_wdf_io_queue_config">WDF_IO_QUEUE_CONFIG</a>.


### -field EvtSerCxFileOpen

A pointer to the controller driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nc-sercx-evt_sercx_fileopen">EvtSerCxFileOpen</a> callback function. This member is optional and can be set to NULL.


### -field EvtSerCxFileClose

A pointer to the controller driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nc-sercx-evt_sercx_fileclose">EvtSerCxFileClose</a> callback function. This member is optional and can be set to NULL.


### -field EvtSerCxFileCleanup

A pointer to the controller driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nc-sercx-evt_sercx_filecleanup">EvtSerCxFileCleanup</a> callback function. This member is optional and can be set to NULL.


### -field EvtSerCxTransmit

A pointer to the controller driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nc-sercx-evt_sercx_transmit">EvtSerCxTransmit</a> callback function. This member is required to point to a valid callback function.


### -field EvtSerCxReceive

A pointer to the controller driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nc-sercx-evt_sercx_receive">EvtSerCxReceive</a> callback function. This member is required to point to a valid callback function.


### -field EvtSerCxWaitmask

A pointer to the controller driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nc-sercx-evt_sercx_waitmask">EvtSerCxWaitmask</a> callback function. This member is required to point to a valid callback function.


### -field EvtSerCxPurge

A pointer to the controller driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nc-sercx-evt_sercx_purge">EvtSerCxPurge</a> callback function. This member is optional and can be set to NULL.


### -field EvtSerCxControl

A pointer to the controller driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nc-sercx-evt_sercx_control">EvtSerCxControl</a> callback function. This member is required to point to a valid callback function.


### -field EvtSerCxApplyConfig

A pointer to the controller driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nc-sercx-evt_sercx_apply_config">EvtSerCxApplyConfig</a> callback function. This member is required to point to a valid callback function.


### -field EvtSerCxTransmitCancel

A pointer to the controller driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nc-sercx-evt_sercx_transmit_cancel">EvtSerCxTransmitCancel</a> callback function. This member is optional and can be set to NULL.


### -field EvtSerCxReceiveCancel

A pointer to the controller driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nc-sercx-evt_sercx_receive_cancel">EvtSerCxReceiveCancel</a> callback function. This member is optional and can be set to NULL.


## -remarks



Before this structure is passed to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nf-sercx-sercxinitialize">SerCxInitialize</a> method, it must be initialized by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nf-sercx-sercx_config_init">SERCX_CONFIG_INIT</a> function, and then modified by the controller driver to set the callback function pointers and the <b>PowerManaged</b> member.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nc-sercx-evt_sercx_apply_config">EvtSerCxApplyConfig</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nc-sercx-evt_sercx_control">EvtSerCxControl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nc-sercx-evt_sercx_filecleanup">EvtSerCxFileCleanup</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nc-sercx-evt_sercx_fileclose">EvtSerCxFileClose</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nc-sercx-evt_sercx_fileopen">EvtSerCxFileOpen</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nc-sercx-evt_sercx_purge">EvtSerCxPurge</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nc-sercx-evt_sercx_receive">EvtSerCxReceive</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nc-sercx-evt_sercx_receive_cancel">EvtSerCxReceiveCancel</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nc-sercx-evt_sercx_transmit">EvtSerCxTransmit</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nc-sercx-evt_sercx_transmit_cancel">EvtSerCxTransmitCancel</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nc-sercx-evt_sercx_waitmask">EvtSerCxWaitmask</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nf-sercx-sercx_config_init">SERCX_CONFIG_INIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nf-sercx-sercxinitialize">SerCxInitialize</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfio/ns-wdfio-_wdf_io_queue_config">WDF_IO_QUEUE_CONFIG</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdffdo/nf-wdffdo-wdffdoinitsetfilter">WdfFdoInitSetFilter</a>
 

 

