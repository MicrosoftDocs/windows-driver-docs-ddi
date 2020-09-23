---
UID: NI:ntddvdeo.IOCTL_MIPI_DSI_TRANSMISSION
title: IOCTL_MIPI_DSI_TRANSMISSION
description: Mipi (mobile industry processor interface) DCS IOCLTs must be handled by the monitor, oem-panel, or port/miniport driver.
tech.root: display
ms.assetid: 7292a449-2c3c-4409-a031-ffe6316767f6
ms.date: 03/24/2020
req.header: ntddvdeo.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: 
req.ddi-compliance: 
req.max-support: 
targetos: Windows
f1_keywords:
 - IOCTL_MIPI_DSI_TRANSMISSION
 - ntddvdeo/IOCTL_MIPI_DSI_TRANSMISSION
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddvdeo.h
api_name:
 - IOCTL_MIPI_DSI_TRANSMISSION
dev_langs:
 - c++
---

# IOCTL_MIPI_DSI_TRANSMISSION IOCTL

### Major Code:  [IRP_MJ_DEVICE_CONTROL](/windows-hardware/drivers/kernel/irp-mj-device-control)


## -description

Mipi (mobile industry processor interface) DCS IOCLTs must be handled by the monitor, oem-panel, or port/miniport driver.

## -ioctlparameters

### -input-buffer

n/a

### -input-buffer-length

n/a

### -output-buffer

n/a

### -output-buffer-length

n/a

### -in-out-buffer

A [**DXGK_DSI_TRANSMISSION**](../dispmprt/ns-dispmprt-dxgk_dsi_transmission.md) structure followed by [**DXGK_DSI_PACKET**](../dispmprt/ns-dispmprt-dxgk_dsi_packet.md) structures containing the packets.

### -inout-buffer-length

At least ```sizeof(DXGK_DSI_TRANSMISSION) + ((PacketCount - 1) * sizeof(DXGK_DSI_PACKET)) + FinalPacketExtraPayload```. See Remarks for details.

### -status-block

Irp->IoStatus.Status is set to STATUS_SUCCESS if the request is successful.
Otherwise, Status to the appropriate error condition as a NTSTATUS code. 
For more information, see [NTSTATUS Values](/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks

Mobile Industry Processor Interface (MIPI) Digital Serial Interface(DSI) IOCTLs must be handled by the monitor, oem-panel, or port/miniport driver.

### Performing Transmissions

To allow a panel driver to interact over this otherwise private interface between the graphics adapter and panel hardware, the transactions must either have no graphics driver effect, other than time occupying the bus, or they must be fully defined so that the graphics driver is in control. Since the point of allowing a panel driver to interact is to provide support for custom panel features which are opaque to the graphics driver, fully defined operations are intended to be restricted to transactions where the panel driver needs to perform a standardized operation which cannot be performed without the graphics driver involvement. Such transactions will be treated as exceptions routed explicitly rather than as transmissions.

Each transmission request consists of a single buffer which is filled by the OEM panel driver, passed down the monitor stack and returned with the results of the transmission, if any. The buffer contains overall information about the transmission, with both input and output fields, followed by a variable sized array of [**DXGK_DSI_PACKET**](../dispmprt/ns-dispmprt-dxgk_dsi_packet.md) structures. The packets are described in DSI terms, such that any DSI packet can be described however the OS will parse the packets and reject any transmission that includes disallowed packets. All packets except the last are, by DSI definition, write packets that may be either short writes, in which case the **Payload** buffer is unused, or long writes which fit within the **Payload** buffer. The last packet in a transmission, which may be a read or a write, is allowed to use an extended payload by allocating and describing a larger buffer which will allows space for reads or writes of any size up to the DSI long packet data limit of 64K-1 data bytes. This allows sequences of small write packets to be queued to the driver in a single call but does require that larger packets are sent individually. The value of the **FinalPacketExtraPayload** field indicates how many extra bytes have been allocated but this must also be accounted for in the **TotalBufferSize** field.

The OEM panel driver is responsible for ensuring that the transmissions it requests do not conflict or interfere with other transmissions that the graphics driver uses for normal interaction with the panel due to excessive requests or requesting operations which would cause delays in processing other transmissions. The panel driver must not change any state which would cause subsequent failures in the graphics driver, for example changing the panel timing via MCS commands. Similarly, if the OS has requested a display change, via the graphics driver, for example an increase in brightness, the panel driver must not use DSI commands to undo that change, either in response or for other purposes.

**IOCTL_MIPI_DSI_TRANSMISSION** is used to request a transmission to the peripheral containing one or more DSI packets. The panel driver must always initialize **TotalBufferSize**, **PacketCount** and the first three BYTES of each packet. The panel driver may override the default behavior using non-zero values for **TransmissionMode**, **ReportMipiErrors**, **ClearMipiErrors**, **SecondaryPort**, **ManufacturingMode** and **FinalCommandExtraPayload**. All uninitialized values must be set to zero.

The OS will ensure that the sequence of DSI packets is well-formed, with valid info in all defined fields and correct buffer sizes. The OS is responsible for initializing the **FailedPacket** field to DXGK_DSI_INVALID_PACKET_INDEX so that further validation in the OS or driver only needs to set the field if a problem is found with a particular packet. If the [**DXGK_DSI_TRANSMISSION**](../dispmprt/ns-dispmprt-dxgk_dsi_transmission.md) is not well-formed, the OS will set the DXGK_HOST_DSI_INVALID_TRANSMISSION flag in the **HostErrors** field to distinguish this from other invalid params errors.

To be considered well-formed, the following must all be true:

- TotalBufferSize >= sizeof(DXGK_DSI_TRANSMISSION) + ((PacketCount - 1) * sizeof(DXGK_DSI_PACKET)) + FinalPacketExtraPayload
- FinalPacketExtraPayload <= 64K-1-DXGK_DSI_PACKET_EMBEDDED_PAYLOAD_SIZE (0xFFF7)
- TotalBufferSize <= ROUND_TO_PAGES( sizeof(DXGK_DSI_TRANSMISSION) + (0xFE * sizeof(DXGK_DSI_PACKET)) + 0xFFF7 )
- PacketCount != 0
- Only the last packet is allowed to be a read
- Only a final long write packet can have a LongWriteWordCount value larger than DXGK_DSI_PACKET_EMBEDDED_PAYLOAD_SIZE

### Packet Validation

Although the OS will not attempt to fully validate the content of all packets, it will reject a transmission containing any DSI commands other than the following, completing the IOCTL without calling the graphics driver:

Data type value | Description
---- | ----------------------------------
0x03 | Generic Short WRITE, no parameters
0x13 | Generic Short WRITE, 1 parameter
0x23 | Generic Short WRITE, 2 parameters
0x04 | Generic READ, no parameters
0x14 | Generic READ, 1 parameter
0x24 | Generic READ, 2 parameters
0x05 | DCS Short WRITE, no parameters
0x15 | DCS Short WRITE, 1 parameter
0x06 | DCS READ, no parameters
0x29 | Generic Long Write
0x39 | DCS Long Write/write_LUT

Generic read and write commands require understanding the panel specification so the expectation is that these commands can be used freely by the panel driver without causing problems for the graphics driver as long as the bus is not used excessively.  Similarly, DCS MCS commands are explicitly defined for manufacturer use so there should be no problem with interference between the graphics driver and the panel driver.

For DCS UCS, undefined commands are not expected to be used by the graphics driver, so the OS will allow them to be used by the panel driver although there is clearly a risk that future [MIPI-DCS](#MIPI-DCS) spec changes define the command so MCS commands are preferred.

Standardized DCS UCS commands will be used by the graphics driver during normal operation and are potentially usable by the panel driver so the risk of commands sent by the OEM panel driver causing problems with subsequent graphics driver commands needs to be mitigated.  To do this, the OS will parse DCS commands and reject packets which are expected to cause conflicts unless the OEM panel driver sets the `ManufacturingMode` flag and the OS confirms that the system is in manufacturing mode.  If the flag is set but the system is not in manufacturing mode, the transmission IOCTL will be completed with the [DXGK_HOST_DSI_INVALID_TRANSMISSION](#DXGK_HOST_DSI_INVALID_TRANSMISSION) flag set in the `HostErrors` field without calling the graphics driver.

Conditions which would require a fully defined transaction instead of using a transmission would be where:

- Timed idle periods are required before or after, such as DCS soft_reset
- Changing the operating environment for frame output, such as DCS set_vsync_timing and enter_sleep_mode
- Using transactions with start/continue semantics where the graphics driver may also need to access the same data, such as DCS write_memory_start/write_memory_continue

In addition, there are classes of DCS commands that will be rejected by the OS when sent as a transmission:

- Any command which would need to be fully defined, as described above
- Reads of pixel data which could be used for screen scraping
- Writes of pixel data

UCS commands that the OS will pass through to the graphics driver

Hex | Command
--- | -------
00h | nop
26h | set_gamma_curve
2Dh | write_LUT
51h | set_display_brightness
52h | get_display_brightness
53h | write_control_display
54h | get_control_display
55h | write_power_save
56h | get_power_save
5Eh | set_CABC_min_brightness
5Fh | get_CABC_min_brightness
03h | get_compression_mode
05h | get_error_count_on_DSI
06h | get_red_channel
07h | get_green_channel
08h | get_blue_channel
0Ah | get_power_mode
0Bh | get_address_mode
0Ch | get_pixel_format
0Dh | get_display_mode
0Eh | get_signal_mode
0Fh | get_diagnostic_result
14h | get_image_checksum_rgb
15h | get_image_checksum_ct
3Fh | get_3D_control
45h | get_scanline

UCS commands that the OS will reject

Hex | Command
--- | -------
01h | soft_reset - note, this must be sent via an [IOCTL_MIPI_DSI_RESET](#IOCTL_MIPI_DSI_RESET)
10h | enter_sleep_mode
11h | exit_sleep_mode
12h | enter_partial_mode
13h | enter_normal_mode
20h | exit_invert_mode
21h | enter_invert_mode
28h | set_display_off
29h | set_display_on
2Ah | set_column_address
2Bh | set_page_address
2Ch | write_memory_start
2Eh | read_memory_start
30h | set_partial_rows
31h | set_partial_columns
33h | set_scroll_area
34h | set_tear_off
35h | set_tear_on
36h | set_address_mode
37h | set_scroll_start
38h | exit_idle_mode
39h | enter_idle_mode
3Ah | set_pixel_format
3Ch | write_memory_continue
3Dh | set_3D_control
3Eh | read_memory_continue
40h | set_vsync_timing
44h | set_tear_scanline
A1h | read_DDB_start
A2h | read_PPS_start
A8h | read_DDB_continue
A9h | read_PPS_continue

> [!NOTE]
> The OS validation policies may be modified in future releases.

### Graphics Driver Implementation

If the transmission passes OS validation, the OS passes the buffer to the graphics driver using [**DsiTransmission**](../dispmprt/nc-dispmprt_dxgk_dsitransmission.md).

Adding OEM transmissions into an interface which is already being used to send both pixel and control data based on OS requests and the needs of peripheral control, inevitably means that the graphics driver will need to enhance its internal sequencing to ensure that this additional stream of packets can be incorporated correctly. The graphics driver must not reorder packets within a transmission from the OEM panel driver and must send the entire sequence uninterrupted and without interleaving of other packets. The graphics driver is not required to maintain the order of its own packets with respect to the time of arrival of OEM panel transmission request, so may elect to send packets to set up the following frame before (or after) sending an OEM panel transmission. If completion of a started OEM panel transmission threatens to cause critical packets to miss their time window, the driver should report the transmission as cancelled. If a transmission has not started but the driver expects it to cause critical packets to miss their time window, the driver should defer starting the transmission until the next blanking period.  If deferring an OEM panel transmission would cause it to have been waiting for more than two frames to start, the driver should report the transmission as dropped.

It is not possible for a graphics driver to ensure that the transmissions it is sending on behalf of the panel driver do not conflict with the transmissions over which it has control.  The driver may choose to inspect packets within a transmission and reject the transmission if they would cause problems but any packets which are considered to be unsafe should be flagged for OS level rejection, so driver level rejection should ideally be due to graphics vendor specific concerns. The driver must not attempt to cache or optimize either reads or writes, even if the packets appear to be standardized commands.

If the graphics driver rejects a transmission due to a problem with a packet, it must update the `FailedPacket` field with the index of the first packet causing the transmission to be rejected and set the `HostErrors` DXGK_HOST_DSI_DRIVER_REJECTED_PACKET flag before returning.  If a transmission mode override is provided, the driver should verify that the override is compatible with its hardware constraints and if not, set the `HostErrors` DXGK_HOST_DSI_BAD_TRANSMISSION_MODE flag before returning.

If a failure occurs during communication, the graphics driver should update the `FailedPacket` field with the index of the packet which failed however it may not be possible in all cases for the driver to identify the packet so the driver should leave the default value, DXGK_DSI_INVALID_PACKET_INDEX, for such cases.

The graphics driver is responsible for the communication of the packets so must ensure any check sums are calculated and verified. Any transmission which ends with a read, will be a short packet, so the Data0 and Data1 fields contain any parameters and the response may be either a short or long packet.  The graphics driver may not know which form and how long the returned data will be but the maximum size is the full size of the payload for the final packet, including the `FinalPacketExtraPayload`.  The OS will validate that this value is no larger than the `TargetMaximumReturnPacketSize` reported by the driver in its capabilities for the target but the driver must ensure both that this buffer is not overrun by a peripheral reporting more data, and that data from the peripheral is not truncated due to being larger than the MaximumReturnPacketSize currently applied to the peripheral.  The driver writes the number of bytes read into the buffer into the `ReadWordCount` field describing the transmission.

There may be cases where the graphics driver is forced to reset either the communications interface to the panel, or the whole panel due to errors which may not be related to and may not be observable to the OEM panel driver. To deal with this, the driver must report either DXGK_HOST_DSI_INTERFACE_RESET or DXGK_HOST_DSI_DEVICE_RESET set in the `HostErrors` field on the first transmission attempt following the reset so that the OEM panel driver can detect the situation and recover.  The driver must not send this transmission to the hardware but the OEM panel driver may simply retry the same command if no recovery is required, in which case the driver should proceed with processing the transmission as usual.

### Completing a Transmission

When the IOCTL completes the `FailedPacket`, `ReadWordCount`, `MipiErrors`, `HostErrors` and payload for a read (final) packet may have been updated depending on the outcome.  If errors were found while processing the transmission, the OEM panel driver needs to use the `MipiErrors` and `HostErrors` output values to determine how to recover and proceed.

To ensure that output is returned to the caller to provide details of any errors, IOCTL and DDI calls need to report a success, even if errors are found.  Success does not indicate that the transaction was successful, it indicates that the calls to handle the transaction proceeded as expected and error flags have been set, if appropriate.  Failures may still be reported for conditions such as an unsupported DDI call (presumably due to a driver mismatch), memory allocation failures or passing completely bad parameters, such as passing a NULL buffer.  If no errors are reported for a successful call, the caller should assume that the transaction was successful.

## -see-also

[**DsiTransmission**](../dispmprt/nc-dispmprt_dxgk_dsitransmission.md)

[**DXGK_DSI_PACKET**](../dispmprt/ns-dispmprt-dxgk_dsi_packet.md)

[**DXGK_DSI_TRANSMISSION**](../dispmprt/ns-dispmprt-dxgk_dsi_transmission.md)

[**IOCTL_MIPI_DSI_QUERY_CAPS**](ni-ntddvdeo-ioctl_mipi_dsi_query_caps.md)

[**IOCTL_MIPI_DSI_RESET**](ni-ntddvdeo-ioctl_mipi_dsi_reset.md)