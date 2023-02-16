---
UID: NS:gnssdriver.GNSS_DRIVERCOMMAND_PARAM
title: GNSS_DRIVERCOMMAND_PARAM (gnssdriver.h)
description: The GNSS_DRIVERCOMMAND_PARAM structure is used to send a command to the GNSS driver.
tech.root: gnss
ms.date: 06/20/2022
keywords: ["GNSS_DRIVERCOMMAND_PARAM structure"]
ms.keywords: "*PGNSS_DRIVERCOMMAND_PARAM, GNSS_DRIVERCOMMAND_PARAM, GNSS_DRIVERCOMMAND_PARAM structure [Sensor Devices], PGNSS_DRIVERCOMMAND_PARAM, PGNSS_DRIVERCOMMAND_PARAM structure pointer [Sensor Devices], gnss.gnss_drivercommand_param, gnssdriver/GNSS_DRIVERCOMMAND_PARAM, gnssdriver/PGNSS_DRIVERCOMMAND_PARAM"
req.header: gnssdriver.h
req.include-header: Gnssdriver.h
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
targetos: Windows
req.typenames: GNSS_DRIVERCOMMAND_PARAM, *PGNSS_DRIVERCOMMAND_PARAM
f1_keywords:
 - PGNSS_DRIVERCOMMAND_PARAM
 - gnssdriver/PGNSS_DRIVERCOMMAND_PARAM
 - GNSS_DRIVERCOMMAND_PARAM
 - gnssdriver/GNSS_DRIVERCOMMAND_PARAM
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - gnssdriver.h
api_name:
 - PGNSS_DRIVERCOMMAND_PARAM
 - GNSS_DRIVERCOMMAND_PARAM
---

## -description

The **GNSS_DRIVERCOMMAND_PARAM** structure is used to send a command to the GNSS driver.

The command may involve configuring certain parameters and state variables of the underlying GNSS driver or device, or executing certain defined actions through the driver.

## -struct-fields

### -field Size

Structure size.

### -field Version

Version number.

### -field CommandType

Identifies the specific command that the driver is required to execute.

This is a well-defined list of GNSS driver commands, as defined by the [GNSS_DRIVERCOMMAND_TYPE](./ne-gnssdriver-gnss_drivercommand_type.md) enumeration.

### -field Reserved

Reserved for future use.

### -field CommandDataSize

Size of the configuration data being sent to the driver.

### -field Unused

Padding buffer reserved for future use.

### -field CommandData

Data associated with the specific command type.

The driver must cast this buffer to the appropriate data type depending on the specific command.

