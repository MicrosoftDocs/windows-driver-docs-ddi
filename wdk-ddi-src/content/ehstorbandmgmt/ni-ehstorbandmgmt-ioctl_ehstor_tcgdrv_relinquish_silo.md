---
UID: NI:ehstorbandmgmt.IOCTL_EHSTOR_TCGDRV_RELINQUISH_SILO
title: IOCTL_EHSTOR_TCGDRV_RELINQUISH_SILO (ehstorbandmgmt.h)
description: The IOCTL_EHSTOR_TCGDRV_RELINQUISH_SILO request relinquishes control of band management by the Trusted Computing Group (TCG) Storage Silo driver.
old-location: storage\ioctl_ehstor_tcgdrv_relinquish_silo.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["IOCTL_EHSTOR_TCGDRV_RELINQUISH_SILO IOCTL"]
ms.keywords: IOCTL_EHSTOR_TCGDRV_RELINQUISH_SILO, IOCTL_EHSTOR_TCGDRV_RELINQUISH_SILO control, IOCTL_EHSTOR_TCGDRV_RELINQUISH_SILO control code [Storage Devices], ehstorbandmgmt/IOCTL_EHSTOR_TCGDRV_RELINQUISH_SILO, storage.ioctl_ehstor_tcgdrv_relinquish_silo
req.header: ehstorbandmgmt.h
req.include-header: EhStorBandMgmt.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8
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
 - IOCTL_EHSTOR_TCGDRV_RELINQUISH_SILO
 - ehstorbandmgmt/IOCTL_EHSTOR_TCGDRV_RELINQUISH_SILO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - EhStorBandMgmt.h
api_name:
 - IOCTL_EHSTOR_TCGDRV_RELINQUISH_SILO
---

# IOCTL_EHSTOR_TCGDRV_RELINQUISH_SILO IOCTL


## -description

The <b>IOCTL_EHSTOR_TCGDRV_RELINQUISH_SILO</b> request relinquishes control of band management by the Trusted Computing Group (TCG) Storage Silo driver.  Applications issue this request to manage a storage silo directly. The band management functionality and API provided by the TCG Storage Silo driver are disabled.

## -ioctlparameters

### -ioctl-major-code

### -input-buffer

None.

### -input-buffer-length

None.

### -output-buffer

None.

### -output-buffer-length

None.

### -in-out-buffer

### -inout-buffer-length

### -status-block

On return, the <b>Status</b> field will contain STATUS_SUCCESS if the operation was successful. Otherwise, another appropriate status code is returned.

## -remarks

When the TCG Storage Silo driver relinquishes control, all band management IOCTLs registered by an <a href="/windows-hardware/drivers/ddi/ehstorioctl/ni-ehstorioctl-ioctl_ehstor_driver_report_capabilities"> IOCTL_EHSTOR_DRIVER_REPORT_CAPABILITIES</a> request are unregistered. Any band management IOCTL requests received are returned with STATUS_INVALID_DEVICE_REQUEST. 

After relinquishing control, the TCG Storage Silo driver can regain control of a storage device when the device is stopped and restarted.

To prevent the TCG Storage Silo driver from reconfiguring the TCG subsystem in a mode compatible with Windows after restart, the SID credential should be changed to a nondefault value or SID authority should be disabled. This will also allow direct management of a storage silo.

## -see-also

<a href="/windows-hardware/drivers/ddi/ehstorioctl/ni-ehstorioctl-ioctl_ehstor_driver_report_capabilities">IOCTL_EHSTOR_DRIVER_REPORT_CAPABILITIES</a>
