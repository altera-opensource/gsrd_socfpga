# Intel SoCFPGA Golden Software Reference Design

GSRD is an Embedded Linux Reference Distribution optimized for SoCFPGA.  
It is based on Yocto Project Poky reference distribution.

## Meta Layers

* meta-intel-fpga - SoCFPGA BSP Core Layer
* meta-intel-fpga-refdes - SoCFPGA GSRD Customization Layer

Dependencies
* poky - Core Layer from Yocto Project
* meta-openembedded - Additional features (python, networking tools, etc) for GSRD

## Using The Script
#### [Default GSRD Setup](#default-gsrd-setup-1)  
#### [Default GSRD Setup with eSDK](#default-gsrd-setup-with-esdk-1)  
#### [Custom GSRD Setup](#custom-gsrd-setup-1)  

## Supported Image Variant:  

|    Target                  |              Image                           |
| -------------------------- | -------------------------------------------- |
| Agilex5                    |   gsrd                                       |
| Agilex5 DK-A5E065BB32AES1  |   gsrd [ qspi + emmc ], nand                 |
| Agilex5 DK-A5E013BB32AESI0 |   gsrd [ qspi + emmc ], nand                 |
| Agilex5 Modular            |   gsrd                                       |
| Agilex7 DK-SI-AGF014EA     |   gsrd [ sgmii + pr + qspi ]                 |
| Agilex7 DK-SI-AGF014EB     |   gsrd [ sgmii + pr + qspi ]                 |
| Agilex7 DK-DEV-AGF027F1ES  |   gsrd                                       |
| Agilex7 DK-SI-AGI027FB     |   gsrd                                       |
| Agilex7 DK-SI-AGI027FA     |   gsrd                                       |
| Agilex7 DK-DEV-AGM039FES   |   gsrd                                       |
| Stratix10                  |   gsrd [ sgmii + pr + qspi ]                 |
| Stratix10 H-Tile           |   gsrd [ pr + qspi ]                         |
| Arria10                    |   gsrd, qspi, nand, pcie, pr, sgmii, tse     |
| Cyclone5                   |   gsrd                                       |
| Default                    |   gsrd                                       |


## Default GSRD Setup

1. Clone the repository  
`$ git clone -b $POKY_VERSION https://github.com/altera-opensource/gsrd-socfpga.git`
2. Sync the submodules  
`$ cd gsrd-socfpga`  
`$ git submodule update --init -r`
3. Source the script to export component version (Linux,U-Boot,ATF,Machine,Image)  

|  Target                    |            Command                             |
| -------------------------- | ---------------------------------------------- |
| Agilex5                    | $ . agilex5-gsrd-build.sh                      |
| Agilex5 DK-A5E065BB32AES1  | $ . agilex5_dk_a5e065bb32aes1-$Image-build.sh  |
| Agilex5 DK-A5E013BB32AESI0 | $ . agilex5_dk_a5e013bb32aesi0-$Image-build.sh |
| Agilex5 Modular            | $ . agilex5_modular-gsrd-build.sh              |
| Agilex7 DK-SI-AGF014EA     | $ . agilex7_dk_si_agf014ea-gsrd-build.sh       |
| Agilex7 DK-SI-AGF014EB     | $ . agilex7_dk_si_agf014eb-gsrd-build.sh       |
| Agilex7 DK-DEV-AGF027F1ES  | $ . agilex7_dk_dev_agf027f1es-gsrd-build.sh    |
| Agilex7 DK-SI-AGI027FB     | $ . agilex7_dk_si_agi027fb-gsrd-build.sh       |
| Agilex7 DK-SI-AGI027FA     | $ . agilex7_dk_si_agi027fa-gsrd-build.sh       |
| Agilex7 DK-DEV-AGM039FES   | $ . agilex7_dk_dev_agm039fes-gsrd-build.sh     |
| Stratix10                  | $ . stratix10-gsrd-build.sh                    |
| Stratix10 H-Tile           | $ . stratix10_htile-gsrd-build.sh              |
| Arria10                    | $ . arria10-$Image-build.sh                    |
| Cyclone V                  | $ . cyclone5-gsrd-build.sh                     |

4. Build default GSRD setup  
`$ build_default`  

## Default GSRD Setup with eSDK

1. Clone the repository  
`$ git clone -b $POKY_VERSION https://github.com/altera-opensource/gsrd-socfpga.git`
2. Sync the submodules  
`$ cd gsrd-socfpga`  
`$ git submodule update --init -r`
3. Source the script to export component version (Linux,U-Boot,ATF,Machine,Image)  

|  Target                    |            Command                             |
| -------------------------- | ---------------------------------------------- |
| Agilex5                    | $ . agilex5-gsrd-build.sh                      |
| Agilex5 DK-A5E065BB32AES1  | $ . agilex5_dk_a5e065bb32aes1-$Image-build.sh  |
| Agilex5 DK-A5E013BB32AESi0 | $ . agilex5_dk_a5e013bb32aesi0-$Image-build.sh |
| Agilex5 Modular            | $ . agilex5_modular-gsrd-build.sh              |
| Agilex7 DK-SI-AGF014EA     | $ . agilex7_dk_si_agf014ea-gsrd-build.sh       |
| Agilex7 DK-SI-AGF014EB     | $ . agilex7_dk_si_agf014eb-gsrd-build.sh       |
| Agilex7 DK-DEV-AGF027F1ES  | $ . agilex7_dk_dev_agf027f1es-gsrd-build.sh    |
| Agilex7 DK-SI-AGI027FB     | $ . agilex7_dk_si_agi027fb-gsrd-build.sh       |
| Agilex7 DK-SI-AGI027FA     | $ . agilex7_dk_si_agi027fa-gsrd-build.sh       |
| Agilex7 DK-DEV-AGM039FES   | $ . agilex7_dk_dev_agm039fes-gsrd-build.sh     |
| Stratix10                  | $ . stratix10-gsrd-build.sh                    |
| Stratix10 H-Tile           | $ . stratix10_htile-gsrd-build.sh              |
| Arria10                    | $ . arria10-$Image-build.sh                    |
| Cyclone V                  | $ . cyclone5-gsrd-build.sh                     |

4. Build default GSRD setup + eSDK  
`$ build_esdk`  

## Custom GSRD Setup

1. Clone the repository  
`$ git clone -b $POKY_VERSION https://github.com/altera-opensource/gsrd-socfpga.git`
2. Sync the submodules  
`$ cd gsrd-socfpga`  
`$ git submodule update --init -r`
3. Source the script to export component version (Linux,U-Boot,ATF,Machine,Image)  

|  Target                    |            Command                             |
| -------------------------- | ---------------------------------------------- |
| Agilex5                    | $ . agilex5-gsrd-build.sh                      |
| Agilex5 DK-A5E065BB32AES1  | $ . agilex5_dk_a5e065bb32aes1-$Image-build.sh  |
| Agilex5 DK-A5E013BB32AESI0 | $ . agilex5_dk_a5e013bb32aesi0-$Image-build.sh |
| Agilex5 Modular            | $ . agilex5_modular-gsrd-build.sh              |
| Agilex7 DK-SI-AGF014EA     | $ . agilex7_dk_si_agf014ea-gsrd-build.sh       |
| Agilex7 DK-SI-AGF014EB     | $ . agilex7_dk_si_agf014eb-gsrd-build.sh       |
| Agilex7 DK-DEV-AGF027F1ES  | $ . agilex7_dk_dev_agf027f1es-gsrd-build.sh    |
| Agilex7 DK-SI-AGI027FB     | $ . agilex7_dk_si_agi027fb-gsrd-build.sh       |
| Agilex7 DK-SI-AGI027FA     | $ . agilex7_dk_si_agi027fa-gsrd-build.sh       |
| Agilex7 DK-DEV-AGM039FES   | $ . agilex7_dk_dev_agm039fes-gsrd-build.sh     |
| Stratix10                  | $ . stratix10-gsrd-build.sh                    |
| Stratix10 H-Tile           | $ . stratix10_htile-gsrd-build.sh              |
| Arria10                    | $ . arria10-$Image-build.sh                    |
| Cyclone V                  | $ . cyclone5-gsrd-build.sh                     |

4. Setup build environment  
`$ build_setup`
<pre>
5. OPTIONAL:  GHRD:  
              1. Add custom GHRD design in:  
                 $WORKSPACE/meta-intel-fpga-refdes/recipes-bsp/ghrd/files  
                 NOTE: Update/Replace the file with the same naming convention  
                       For Agilex5 DK-A5E065BB32AES1:-  
                                  agilex5_dk_a5e065bb32aes1_gsrd_ghrd.core.rbf 
                                  agilex5_dk_a5e065bb32aes1_nand_ghrd.core.rbf   
                                  agilex5_dk_a5e065bb32aes1_emmc_ghrd.core.rbf  
                                  agilex5_dk_a5e065bb32aes1_tsnconfig2_ghrd.core.rbf
                       For Agilex5 DK-A5E013BB32AESI0:-
                                  agilex5_dk_a5e013bb32aesi0_gsrd_ghrd.core.rbf
                                  agilex5_dk_a5e013bb32aesi0_nand_ghrd.core.rbf
                                  agilex5_dk_a5e013bb32aesi0_emmc_ghrd.core.rbf
                       For Agilex5 Modular:-  
                                  agilex5_modular_gsrd_ghrd.core.rbf 
                       For Agilex7 DK-SI-AGF014EA:-  
                                  agilex7_dk_si_agf014ea_gsrd_ghrd.core.rbf  
                                  agilex7_dk_si_agf014ea_nand_ghrd.core.rbf  
                                  agilex7_dk_si_agf014ea_pr_ghrd.core.rbf  
                                  agilex7_dk_si_agf014ea_pr_persona0.rbf  
                                  agilex7_dk_si_agf014ea_pr_persona1.rbf  
                       For Agilex7 DK-SI-AGF014EB:-
                                  agilex7_dk_si_agf014eb_gsrd_ghrd.core.rbf 
                       For Agilex7 DK-DEV-AGF027F1ES:-  
                                  agilex7_dk_dev_agf027f1es_gsrd_ghrd.core.rbf  
                       For Agilex7 DK-SI-AGI027FB:-  
                                  agilex7_dk_si_agi027fb_gsrd_ghrd.core.rbf  
                       For Agilex7 DK-SI-AGI027FA:-  
                                  agilex7_dk_si_agi027fa_gsrd_ghrd.core.rbf 
                       For Agilex7 DK-DEV-AGM039FES:-  
                                  agilex7_dk_dev_agm039fes_gsrd_ghrd.core.rbf 
                       For Stratix10:-  
                                  stratix10_gsrd_ghrd.core.rbf  
                                  stratix10_nand_ghrd.core.rbf  
                                  stratix10_pr_ghrd.core.rbf
                                  stratix10_pr_persona0.rbf  
                                  stratix10_pr_persona1.rbf  
                       For Stratix10 H-Tile:-
                                  stratix10_htile_gsrd_ghrd.core.rbf
                                  stratix10_htile_nand_ghrd.core.rbf
                                  stratix10_htile_pr_ghrd.core.rbf
                                  stratix10_htile_pr_persona0.rbf
                                  stratix10_htile_pr_persona1.rbf
                       For Arria10:-  
                                  GSRD:-  
                                      arria10_gsrd_ghrd_10as066n2.core.rbf  
                                      arria10_gsrd_ghrd_10as066n2.periph.rbf  
                                      arria10_gsrd_hps.xml  
                                  NAND:-  
                                      arria10_nand_ghrd_10as066n2.core.rbf  
                                      arria10_nand_ghrd_10as066n2.periph.rbf  
                                      arria10_nand_hps.xml  
                                  PCIE:-  
                                      arria10_pcie_ghrd_10as066n2.core.rbf  
                                      arria10_pcie_ghrd_10as066n2.periph.rbf  
                                      arria10_pcie_hps.xml  
                                  PR:-  
                                      arria10_pr_ghrd_10as066n2.core.rbf  
                                      arria10_pr_ghrd_10as066n2.periph.rbf  
                                      arria10_pr_hps.xml  
                                      arria10_pr_persona0.rbf  
                                      arria10_pr_persona1.rbf  
                                  QSPI:-  
                                      arria10_qspi_ghrd_10as066n2.core.rbf  
                                      arria10_qspi_ghrd_10as066n2.periph.rbf  
                                      arria10_qspi_hps.xml  
                                  SGMII:-  
                                      arria10_sgmii_ghrd_10as066n2.core.rbf  
                                      arria10_sgmii_ghrd_10as066n2.periph.rbf  
                                      arria10_sgmii_hps.xml  
                                  TSE:-  
                                      arria10_tse_ghrd_10as066n2.core.rbf  
                                      arria10_tse_ghrd_10as066n2.periph.rbf  
                                      arria10_tse_hps.xml  
                       For Cyclone5:-  
                                  cyclone5_gsrd_soc_system.rbf  
              2. Update SRC_URL in the recipe:  
                 $WORKSPACE/meta-intel-fpga-refdes/recipes-bsp/ghrd/hw-ref-design.bb  
                 Note: Update the SRC_URL using the example below  
                       Include the required file with sha256sum  
                 Eg:-  
                       SRC_URI:agilex7_dk_si_agf014ea ?= "\  
                                           file://agilex7_dk_si_agf014ea_gsrd_ghrd.core.rbf;sha256sum=xxxx \  
                                           file://agilex7_dk_si_agf014ea_nand_ghrd.core.rbf;sha256sum=xxxx \  
                                           file://agilex7_dk_si_agf014ea_pr_ghrd.core.rbf;sha256sum=xxxx \  
                                           file://agilex7_dk_si_agf014ea_pr_persona0.rbf;sha256sum=xxxx \  
                                           file://agilex7_dk_si_agf014ea_pr_persona1.rbf;sha256sum=xxxx \  
                                           "  
              U-BOOT:  
                 For Agilex and Stratix10:-  
                     Edit uboot.txt, uboot_script.its in:  
                     $WORKSPACE/meta-intel-fpga-refdes/recipes-bsp/u-boot/files  
                     Edit fit_kernel_(agilex*/stratix10).its in:  
                     $WORKSPACE/meta-intel-fpga-refdes/recipes-kernel/linux/linux-socfpga-lts  
                 For Cyclone5:-  
                     Edit cyclone5_u-boot.txt in:  
                     $WORKSPACE/meta-intel-fpga-refdes/recipes-bsp/u-boot/files  
</pre>
6. Perform Yocto bitbake to generate binaries  
`$ bitbake_image`
7. Package binaries into build folder  
`$ package`  