---
UID: NS:sercx._SERCX2_CONFIG
title: _SERCX2_CONFIG (sercx.h)
description: The SERCX2_CONFIG structure contains configuration information for version 2 of the serial framework extension (SerCx2).
old-location: serports\sercx2_config.htm
tech.root: serports
ms.date: 04/23/2018
keywords: ["SERCX2_CONFIG structure"]
ms.keywords: "*PSERCX2_CONFIG, 2/PSERCX2_CONFIG, 2/SERCX2_CONFIG, PSERCX2_CONFIG, PSERCX2_CONFIG structure pointer [Serial Ports], SERCX2_CONFIG, SERCX2_CONFIG structure [Serial Ports], _SERCX2_CONFIG, serports.sercx2_config"
req.header: sercx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 8.1.
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
req.typenames: SERCX2_CONFIG, *PSERCX2_CONFIG
f1_keywords:
 - _SERCX2_CONFIG
 - sercx/_SERCX2_CONFIG
 - PSERCX2_CONFIG
 - sercx/PSERCX2_CONFIG
 - SERCX2_CONFIG
 - sercx/SERCX2_CONFIG
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - 2.0\Sercx.h
api_name:
 - _SERCX2_CONFIG
 - PSERCX2_CONFIG
 - SERCX2_CONFIG
---

# _SERCX2_CONFIG structure


## -description

The <b>SERCX2_CONFIG</b> structure contains configuration information for version 2 of the serial framework extension (SerCx2).

## -struct-fields

### -field Size

The size, in bytes, of this structure. The <a href="/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2initializedevice">SerCx2InitializeDevice</a> method uses this member to determine which version of the structure the caller is using. The size of this structure might change in future versions of the Sercx.h header file.

### -field EvtSerCx2FileOpen

A pointer to the driver-implemented <a href="/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_fileopen">EvtSerCx2FileOpen</a> event callback function. This member is optional and can be set to <b>NULL</b> to indicate that the driver does not implement the function. However, a driver that implements this function must also implement an <i>EvtSerCx2FileClose</i> function.

### -field EvtSerCx2FileClose

A pointer to the driver-implemented <a href="/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_fileclose">EvtSerCx2FileClose</a> event callback function. This member is optional and can be set to <b>NULL</b> to indicate that the driver does not implement the function.

### -field EvtSerCx2SetWaitMask

A pointer to the driver-implemented <a href="/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_set_wait_mask">EvtSerCx2SetWaitmask</a> event callback function. This member must point to a valid function.

### -field EvtSerCx2PurgeFifos

A pointer to the driver-implemented <a href="/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_purge_fifos">EvtSerCx2PurgeFifos</a> event callback function. This member must point to a valid function.

### -field EvtSerCx2Control

A pointer to the driver-implemented <a href="/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_control">EvtSerCx2Control</a> event callback function. This member must point to a valid function.

### -field EvtSerCx2ApplyConfig

A pointer to the driver-implemented <a href="/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_apply_config">EvtSerCx2ApplyConfig</a> event callback function. This member must point to a valid function.

### -field EvtSerCx2SelectNextReceiveTransactionType

A pointer to the driver-implemented <a href="/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_select_next_receive_transaction_type">EvtSerCx2SelectNextReceiveTransactionType</a> event callback function. This member is optional and can be set to <b>NULL</b> to indicate that the driver does not implement the function.

### -field EvtSerCx2SelectNextTransmitTransactionType

A pointer to the driver-implemented <a href="/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_select_next_transmit_transaction_type">EvtSerCx2SelectNextTransmitTransactionType</a> event callback function. This member is optional and can be set to <b>NULL</b> to indicate that the driver does not implement the function.

### -field RequestAttributes

A pointer to a <a href="/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure that describes the attributes to assign to the framework request objects that SerCx2 passes to the serial controller driver. Before calling the <a href="/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2initializedevice">SerCx2InitializeDevice</a> method, the caller must call the <a href="/windows-hardware/drivers/ddi/wdfobject/nf-wdfobject-wdf_object_attributes_init">WDF_OBJECT_ATTRIBUTES_INIT</a> function to initialize the structure. This member is optional and can be specified as WDF_NO_OBJECT_ATTRIBUTES if the serial controller driver does not need to assign attributes to the object. For more information, see Remarks.

## -remarks

The <a href="/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2initializedevice">SerCx2InitializeDevice</a> method accepts a pointer to a <b>SERCX2_CONFIG</b> structure as an input parameter. Before calling <b>SerCx2InitializeDevice</b>, call the <a href="/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2_config_init">SERCX2_CONFIG_INIT</a> function to initialize this structure.

If the <b>RequestAttributes</b> member points to a <b>WDF_OBJECT_ATTRIBUTES</b> structure, the caller must not overwrite the values that the <a href="/windows-hardware/drivers/ddi/wdfobject/nf-wdfobject-wdf_object_attributes_init">WDF_OBJECT_ATTRIBUTES_INIT</a> initialization function writes to the <b>ParentObject</b>, <b>ExecutionLevel</b>, and <b>SynchronizationScope</b> members of this structure.

A driver might need to store information in context areas in the framework request objects that the driver receives. Typically, the driver calls the <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitsetrequestattributes">WdfDeviceInitSetRequestAttributes</a> method to specify the required attributes for request objects. These attributes include the name and size of the context area in each request object. Additionally, in the current implementation of SerCx2, a serial controller driver that requires a request context should specify these same attributes in the <b>RequestAttributes</b> member of the <b>SERCX2_CONFIG</b> structure that the driver passes to <b>SerCx2InitializeDevice</b>. That is, the driver should specify the same request attributes twice—in the <b>SerCx2InitializeDevice</b> call, and in the <b>WdfDeviceInitSetRequestAttributes</b> call. For more information, see <a href="/previous-versions/dn265314(v=vs.85)">SerCx2 Custom-Receive Transactions</a> and <a href="/previous-versions/dn265320(v=vs.85)">SerCx2 Custom-Transmit Transactions</a>.

A driver that never needs a request context does not need to call <b>WdfDeviceInitSetRequestAttributes</b>, and can set the <b>RequestAttributes</b> member of the <b>SERCX2_CONFIG</b> structure to WDF_NO_OBJECT_ATTRIBUTES.

## -see-also

<a href="/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_apply_config">EvtSerCx2ApplyConfig</a>



<a href="/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_control">EvtSerCx2Control</a>



<a href="/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_fileclose">EvtSerCx2FileClose</a>



<a href="/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_fileopen">EvtSerCx2FileOpen</a>



<a href="/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_purge_fifos">EvtSerCx2PurgeFifos</a>



<a href="/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_select_next_receive_transaction_type">EvtSerCx2SelectNextReceiveTransactionType</a>



<a href="/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_select_next_transmit_transaction_type">EvtSerCx2SelectNextTransmitTransactionType</a>



<a href="/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_set_wait_mask">EvtSerCx2SetWaitmask</a>



<a href="/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2_config_init">SERCX2_CONFIG_INIT</a>



<a href="/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2initializedevice">SerCx2InitializeDevice</a>



<a href="/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a>



<a href="/windows-hardware/drivers/ddi/wdfobject/nf-wdfobject-wdf_object_attributes_init">WDF_OBJECT_ATTRIBUTES_INIT</a>

