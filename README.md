# GnGeo: Neo-Geo Emulator for GNU/Linux

### GnGeo Emulator means

GnGeo is a Neo-Geo emulator for GNU/Linux platform it has a driver system
much like that of MAME and is quite fast.

Dependencies for Debian/Ubuntu Linux:
-------------------------------------

    # apt install gawk libsdl1.2-dev libsdl-image1.2-dev nasm zlib1g-dev

Required firmware (BIOS):
-------------------------

To play some games on the emulator, you need to have the proprietary
Neo-Geo firmware (BIOS).

The necessary firmwares are:

 * 000-lo.lo
 * aes-bios.bin (A.E.S)
 * asia-s3.rom (Asia)
 * sp-s2.sp1 (Europe)
 * usa_2slt.bin (USA)
 * uni-bios.rom
 * vs-bios.rom (Japan)

All files have to be zipped in "**neogeo.zip**" and this file has to be placed
in the roms directory within GnGeo.

> **uni-bios.rom** - You can download the latest version at
> this link: http://unibios.free.fr

If have similar files as: (*sfix.sfix, sm1.sm1*), just rename them properly.

You can configure your bios in **$HOME/.gngeo/gngeorc**.

### License:

The GnGeo project as a whole is distributed under the terms of the
[GNU General Public License, version 2](https://www.gnu.org/licenses/gpl-2.0.html)
or later (GPL-2+), since it contains code made available under multiple
GPL-compatible licenses. We would encourage new contributors to distribute
files under this license.

Please see [LICENSE](LICENSE) for further details.

The original code is released under the GPL v2 with this special exception of
this project:

> * You have the permission to link the code of this program with independent
> modules, regardless of the license terms of these independent modules.
>
> * To copy and distribute the resulting executable under terms of your choice,
> provided that you also meet, for each linked independent module, the terms
> and conditions of the license of that module.
>
> * An independent module is a module which is not derived from or based on Gngeo. 
>
> * If you modify this library, you may extend this exception to your version of
> the library, but you are not obligated to do so.
>
> * If you do not wish to do so, delete this exception statement from your version.

---

Please note that GnGeo is a registered trademark of **Mathieu PEPONAS**,
and permission is required to use the "GnGeo" name, logo or wordmark.

The project was governed by a GPL v2 license that can be found in the files.

- © 2017 Project created and re-written by Carlos Donizete Froes [a.k.a coringao]
