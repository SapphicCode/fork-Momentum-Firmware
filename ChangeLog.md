### Breaking Changes:
- VGM: Reworked color customization functionality over RPC (by @HaxSam & @Willy-JL)
  - Better rainbow support, more responsive config, custom fore/back-ground
  - If you used this, need to reflash your VGM and reconfigure the colors
- OFW: CLI: New `top` command, replaces `ps` (by @skotopes)
  - Now includes CPU usage info too

### Added:
- Sub-GHz:
  - New Legrand doorbell protocol (by @user890104)
  - OFW: Princeton protocol add custom guard time (by @Skorpionm & @xMasterX)
- NFC:
  - OFW: Mifare Plus detection support (by @Astrrra)
  - OFW: Felica emulation (by @RebornedBrain)
  - OFW: Write to Ultralight cards is now possible (by @RebornedBrain & @gornekich)
- OFW: RFID: Added Support for Securakey Protocol and RKKTH Plain Text Format (by @zinongli)
- MNTM Settings: Click Ok on Asset Pack setting to choose from a full-screen list (by @Willy-JL)
- JS: Added ADC (analog voltage) support to gpio library (by @jamisonderek)
- FBT: New `SKIP_EXTERNAL` toggle and `EXTRA_EXT_APPS` config option (by @Willy-JL)
- Desktop: Added TV animation from OFW which was missing (internal on OFW)
- UL: BadKB: Add Finnish keyboard layout (by @nicou)
- Furi:
  - OFW: Event loop (by @skotopes)
  - OFW: Thread signals, loader close, loader get app name (by @gsurkov)
- OFW: RPC: Add TarExtract command, some small fixes (by @Willy-JL)
- OFW: USB/CCID: Add initial ISO7816 support (by @kidbomb)
- OFW: FBT/VsCode: Tweaks for cdb generation for clangd (by @hedger)

### Updated:
- Apps:
  - VGM Tool: New RGB VGM firmware to support Flipper FW changes (by @HaxSam)
  - MFKey: 30% speedup, fix half speed mode, fix UI bugs (by @noproto)
  - Picopass: Acknowledgements page, Elite VB6 RNG keygen attack, plugin improvements (by @bettse)
  - Seader: Handle SAM removal better (by @bettse)
  - Authenticator: Fix URL format (by @akopachov)
  - NFC Playlist: Various fixes and improvements, new icon (by @acegoal07)
  - BMI160 Air Mouse: Add support for LSM6DSO (by @alex-vg & @ginkage)
  - UL: ESubGHz Chat: Add back NFC key sharing with nfclegacy (by @xMasterX)
  - UL: Mifare Nested: Free some space by simplifying nfclegacy lib (by @xMasterX)
  - UL: RFID Fuzzer: Fix worker being not in LFRFIDWorkerIdle before next key (by @xMasterX)
  - UL: Barcode: Fix backlight settings (by @xMasterX)
  - OFW: NFC/RFID Detector: Fix some typos (by @Skorpionm)
  - Many apps updated for new refactors (by @Willy-JL & @xMasterX)
- NFC:
  - EMV Transactions menu less nested in UI, hide if data unavailable (by @Willy-JL)
  - Mention using MFKey app after Detect Reader (by @Willy-JL)
  - Cache plugin name not full path, saves some RAM (by @Willy-JL)
  - UL: Better plugin loading, faster launch from favourites, no lag in Saved menu (by @xMasterX)
- Sub-GHz:
  - Refactor Weather protocols in Sub-GHz app, shows only correct data (by @Willy-JL)
  - Streamline generic serialize +1.5k free flash (by @Willy-JL)
- JS: Refactored widget and keyboard modules with `ViewHolder`, fix crash (by @Willy-JL)
- Desktop: Slim down internal anims, +3.4kb free flash (by @Willy-JL)
- CLI: Simpler plugin wrapper +0.5k free flash (by @Willy-JL)
- OFW: Furi: Use static synchronisation primitives, prepare for event loop (by @gsurkov & @skotopes)
- OFW: Code Cleanup: Unused includes, useless checks, unused variables, etc... (by @skotopes)

### Fixed:
- OFW: USB: IRQ, CDC and EP fixes, no more "Operation timeout (generic)" updating from OFW (by @skotopes)
- Sub-GHz:
  - UL: Fix add manually princeton (by @xMasterX)
  - UL: Fix decode raw signals showing up in read menu (by @xMasterX)
  - UL: Sync signal delete scene with OFW (by @xMasterX)
  - UL: Fix incorrect rx key state when opening Read menu (by @xMasterX)
  - OFW: Fixed transition to Saved menu after Delete RAW (by @Skorpionm)
- Archive: Fix favorite's parent folders thinking they are favorited too (by @Willy-JL)
- FBT: Consistent version/branch info, fix gitorigin (by @Willy-JL)
- AssetPacker: Pack pre-compiled icons and fonts too (by @Willy-JL)
- OFW: RPC: Fix input lockup on disconnect (by @Willy-JL)
- OFW: ELF/Flipper application: Do not crash on "out of memory" (by @DrZlo13)
- OFW: JS: Disable logging in mjs +2k free flash (by @hedger)
- OFW: NFC: Fixed infinite loop in dictionary attack scene (by @RebornedBrain)
- OFW: Desktop: Lockup fix, GUI improvements (by @skotopes)
- OFW: Loader: Fix crash on locked via cli loader (by @DrZlo13)
- OFW: Archive: Fix memory leak in favorites add/remove (by @skotopes)
- OFW: Accessor: Disable expansion service on start (by @skotopes)
- OFW: Debug: Backup openocd work area, fix crash after fresh debugger connect and continue (by @skotopes)
- OFW: Cleanup of various warnings from clangd (by @hedger)
- OFW: ReadMe: update outdated bits and pieces (by @skotopes)

### Removed:
- Furi:
  - Temp disabled `FURI_TRACE` due to DFU size, some crashes will say "furi_check failed" instead of source path
  - Reverted TLSF allocator due to diminishing results on RAM usage
- API:
  - Removed unused `Rgb565Color` and `rgb565cmp()` since VGM colors use normal RGB colors now
  - Removed unused `furi_hal_usb_get_config_context()` function since BadKB doesn't use it anymore
- OFW: CLI: Removed `ps` command, replaced by `top`