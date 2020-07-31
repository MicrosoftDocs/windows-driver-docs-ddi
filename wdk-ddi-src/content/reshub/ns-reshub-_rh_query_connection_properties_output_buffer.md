---
UID: NS:reshub._RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER
title: _RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER (reshub.h)
description: The RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER structure contains the connection properties for a target device that is connected to a serial bus (I2C, SPI, or UART).
old-location: spb\rh_query_connection_properties_output_buffer.htm
tech.root: SPB
ms.assetid: 36B2C20C-AA92-4860-9FBC-BA65AFD546E1
ms.date: 02/15/2018
keywords: ["_RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER structure"]
ms.keywords: "*PRH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER, PRH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER, PRH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER structure pointer [Buses], RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER, RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER structure [Buses], SPB.rh_query_connection_properties_output_buffer, _RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER, reshub/PRH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER, reshub/RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER"
f1_keywords:
 - "reshub/RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER"
 - "RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER"
req.header: reshub.h
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
- Reshub.h
api_name:
- RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER
targetos: Windows
req.typenames: RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER, *PRH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER
req.product: Windows 10 or later.
---

# _RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER structure


## -description


The <b>RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER</b> structure contains the connection properties for a target device that is connected to a serial bus (I2C, SPI, or UART).


## -syntax


```cpp
typedef struct _RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER {
  ULONG Version;
  ULONG PropertiesLength;
  UCHAR ConnectionProperties[ANYSIZE_ARRAY];
} RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER, *PRH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER;
```


## -struct-fields




### -field Version

The version number of this structure. This member is set to the RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_VERSION constant, which is defined in the Reshub.h header file.


### -field PropertiesLength

The size, in bytes, of the serial bus connection descriptor that starts with element 0 of the <b>ConnectionProperties</b> array.


### -field ConnectionProperties

The first byte of the serial bus connection descriptor. This byte is immediately followed by the remaining bytes of the descriptor. The <b>PropertiesLength</b> member specifies the total number of bytes occupied by the descriptor. The definition of the <b>ConnectionProperties</b> member uses the ANYSIZE_ARRAY constant, which the Ntdef.h header file defines to be 1. For more information, see Remarks.


## -remarks



The <b>ConnectionProperties</b> member of the <b>RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER</b> structure contains the first byte of the serial bus connection descriptor for the target device. The remaining bytes in the descriptor immediately follow this member in memory. The buffer allocated for the <b>RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER</b> structure is large enough to contain this structure plus the remaining bytes of the serial bus connection descriptor that extend past the end of the structure.

The format for the serial bus connection descriptor is described in the [ACPI 5.0 specification](https://uefi.org/specifications). For convenience, the Reshub.h header file defines the  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/reshub/ns-reshub-_pnp_serial_bus_descriptor">PNP_SERIAL_BUS_DESCRIPTOR</a> structure to enable drivers to access the values in this descriptor.

An SPB controller driver calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spbcx/nf-spbcx-spbtargetgetconnectionparameters">SpbTargetGetConnectionParameters</a> method to get the connection parameters for a target device on a <a href="https://docs.microsoft.com/previous-versions/hh450903(v=vs.85)">simple peripheral bus</a> (typically, I²C or SPI). This method writes the connection parameters to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spbcx/ns-spbcx-_spb_connection_parameters">SPB_CONNECTION_PARAMETERS</a> structure, and the <b>ConnectionParameters</b> member of this structure is a pointer to an <b>RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER</b> structure.

For a code example that uses the <b>RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER</b> structure, see <a href="https://docs.microsoft.com/windows-hardware/drivers/spb/how-to-get-the-connection-settings-for-a-device">How to Get the Connection Settings for a Device</a>.




## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spbcx/ns-spbcx-_spb_connection_parameters">SPB_CONNECTION_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spbcx/nf-spbcx-spbtargetgetconnectionparameters">SpbTargetGetConnectionParameters</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/reshub/ns-reshub-_pnp_serial_bus_descriptor">PNP_SERIAL_BUS_DESCRIPTOR</a>



 

 


