---
UID: NF:ucmtcpcidevice.UCMTCPCI_DEVICE_CONFIG_INIT
title: UCMTCPCI_DEVICE_CONFIG_INIT function (ucmtcpcidevice.h)
description: Initializes the UCMTCPCI_DEVICE_CONFIG structure.
old-location: buses\ucmtcpci_device_config_init.htm
tech.root: usbref
ms.assetid: 8845f8f7-683e-487b-924b-596dbbfb98f2
ms.date: 05/07/2018
keywords: ["UCMTCPCI_DEVICE_CONFIG_INIT function"]
ms.keywords: UCMTCPCI_DEVICE_CONFIG_INIT, UCMTCPCI_DEVICE_CONFIG_INIT method [Buses], buses.ucmtcpci_device_config_init, ucmtcpcidevice/UCMTCPCI_DEVICE_CONFIG_INIT
req.header: ucmtcpcidevice.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - UCMTCPCI_DEVICE_CONFIG_INIT
 - ucmtcpcidevice/UCMTCPCI_DEVICE_CONFIG_INIT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ucmtcpcidevice.h
api_name:
 - UCMTCPCI_DEVICE_CONFIG_INIT
---

# UCMTCPCI_DEVICE_CONFIG_INIT function


## -description

                        Initializes the <a href="/windows-hardware/drivers/ddi/ucmtcpcidevice/ns-ucmtcpcidevice-_ucmtcpci_device_config">UCMTCPCI_DEVICE_CONFIG</a> structure.

## -parameters

### -param Config 

[out]
A pointer to the driver-allocated <a href="/windows-hardware/drivers/ddi/ucmtcpcidevice/ns-ucmtcpcidevice-_ucmtcpci_device_config">UCMTCPCI_DEVICE_CONFIG</a> structure.

## -see-also

<a href="/windows-hardware/drivers/ddi/ucmtcpcidevice/nf-ucmtcpcidevice-ucmtcpcideviceinitialize">UcmTcpciDeviceInitialize</a>