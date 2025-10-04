---
layout: default
---


# Dinoboards Retro Computer Kits

I have designed and developed a number of retro computer kits, based on technology from the 1980s.  They are designed around the RC2014 and RCBus platforms.

There are 2 main sets of kits:

* **Yellow MSX Series** - a series of RC2014/RCBus compatible modules, when connected together allow for a full working reproduction of an original MSX Computer
* **Green Machine Series** - a new series under development based around the eZ80 CPU - the *enhanced Z80* CPU from Zilog


<style>
.journal-highlights {
}
.journal-highlights ul {
  margin: 0 0 1em 0;
  padding: 0;
  list-style: none;
  margin-left: 4em;
  font-family: monospace;
}
.journal-highlights li {
  margin: 0;
  padding: 0 0 0.1em 0;
  display: flex;
  align-items: baseline;
  gap: 0.7em;
}
.journal-highlights .journal-date {
  color: #888;
  font-size: 0.98em;
  min-width: 6.2em;
  display: inline-block;
  text-align: left;
}
.journal-highlights .rss-link {
  transition: color 0.2s, text-decoration 0.2s;
  /* text-decoration: none; */
}
</style>

<div class="journal-highlights">

<p>Follow along with my journey of developing these kits. (<a href="{{ site.baseurl }}/feed.xml" target="_blank" class="rss-link">Atom/RSS Feed Link</a>)</p>

<ul>
{% for post in site.posts limit:3 %}
<li>
  <a href="{{post.url}}"><span class="journal-date">{{ post.date | date: "%Y-%m-%d" }} </span>{{ post.title }}
  </a>
</li>
{% endfor %}
</ul>
</div>

Also checkout my mastodon account for updates and demo videos: <a href="https://mastodon.social/@dinotron/with_replies"  target="_new" style="">
          <img src="{{ site.baseurl }}/assets/mastodon-logo.svg" style="position: relative; top:4px; height: 1em" />&nbsp;mastodon.social/@dinotron
        </a>

<hr/>
# Green Machine Series

The *Green Machine Series* is a series that is still under development, with the *eZ80 for RC* the first kit in the set.  The series goal is to offer as much compatibility as possible with existing RC2014/RCBus module.  With new modules planned to utilise and explore all the capabilities of Zilog's Z80 compatible CPU.

A FAQ for the green series is being constructed.  You can read it here [Green Series FAQ](./green-faq)

### eZ80 for RC

<div class="tags">
  <div class="tag rcbus"></div>
  <div class="tag rc2014"></div>
  <div class="tag romwbw"></div>
</div>

The *eZ80 for RC* is a CPU Module designed for the RCBus and RC2014<strong>&trade;</strong> backplanes.



<div class="product-listing">
  <div>
    <a href="./ez80-for-rc"><img src="{{ site.baseurl }}/assets/images/eZ80-V1.7-installed-profile-front.jpg" alt="eZ80 on RC2014"></a>
  </div>
  <div>
    <p>The eZ80 for RC module is an alternative CPU module for your RC2014 or RCBus based computer.  Upgrade your Z80 to Zilog enhanced version of the chip.  Running at 20Mhz (and overclockable to 40Mhz or more), and take advantage of its many on-chip facilities such as flash ROM, RAM, GPIO and much more.</p>
    <p style="float: left"><a href="./ez80-for-rc">Click here for full details</a></p>
    <div class="buy-on-container">
      <a href="https://shop.dinoboards.com.au/product/ez80-for-rc" class="button" target="_newWindow">
        BUY <img src="/logo-black.png" class="buy-on-shop"/>
      </a>
    </div>
  </div>
</div>

<hr/>


### CH376 USB Module for RC

<div class="tags">
  <div class="tag rcbus"></div>
  <div class="tag rc2014"></div>
  <div class="tag romwbw"></div>
  <div class="tag msx optional"></div>
</div>


Let your Z80 directly enumerate and operate many different types of USB devices, including USB Hubs, Mass Storage, 3.5 USB Floppy drives and USB Keyboards. (With many new device types to be supported in the future)

<div class="product-listing">
  <div>
    <a href="./usb-for-rc"><img src="{{ site.baseurl }}/assets/usb-for-rc/profile.jpg" alt="USB for RCBus/RC2014"></a>
  </div>
  <div>
    <p>The USB for RC module is based on the <a href="#msx-cassette--usb-module">MSX Cassette + USB Module</a>, with the MSX cassette interface components removed.  The native USB drivers written for  MSX-DOS have been ported to RomWBW - enabling full CP/M access to USB Hubs, USB Mass storage, 3.5 USB floppy disk, keyboards and potentially new devices as required drivers are written.</p>
    <p style="float: left"><a href="./usb-for-rc">Click here for full details</a></p>
    <div class="buy-on-container">
      <a href="https://shop.dinoboards.com.au/product/usb-for-rc" class="button" target="_newWindow">
        BUY <img src="/logo-black.png" class="buy-on-shop"/>
      </a>
    </div>
  </div>
</div>

<hr/>

### HDMI for RC

<div class="tags">
  <div class="tag rcbus"></div>
  <div class="tag rc2014"></div>
  <div class="tag romwbw"></div>
  <div class="tag msx optional"></div>
</div>

Tang Nano 20K FPGA driven HDMI Video adapter.

<div class="product-listing">
  <div>
    <a href="./hdmi-for-rc"><img src="{{ site.baseurl }}/assets/hdmi-for-rc/hdmi-profile.jpg" alt="HDMI for RC"></a>
  </div>
  <div>
    <p>A kit based on the Tang Nano 20K FPGA, emulating a V9958 Video Processor Unit - with support for custom extended video modes.  Generate crisp clear video output - learn and and play with a simple-to-use FPGA module</p>
    <p style="float: left"><a href="./hdmi-for-rc">Click here for full details</a></p>
    <div class="buy-on-container">
      <a href="https://shop.dinoboards.com.au/product/hdmi-for-rc" class="button" target="_newWindow">
        BUY <img src="/logo-black.png" class="buy-on-shop"/>
      </a>
    </div>
  </div>
</div>

<hr/>


### 2MB Linear SRAM

<div class="tags">
  <div class="tag rcbus"></div>
  <div class="tag ez80"></div>
</div>


Let your eZ80 break the 64K barrier with this 2MB memory module.  Write applications that can address upto 2 megabytes of RAM, without the need for banking or paging.

<div class="product-listing">
  <div>
    <a href="./2mb-linear-sram"><img src="{{ site.baseurl }}/assets/2mb-linear-sram/pcb-profile.jpg" alt="2MB Linear Memory"></a>
  </div>
  <div>
    <p>Install up to 4 512K SRAM chips to enable your eZ80 to address a total of 2MB of memory directly.</p>
    <p style="float: left"><a href="./2mb-linear-sram">Click here for full details</a></p>
    <div class="buy-on-container">
      <a href="https://shop.dinoboards.com.au/product/2mb-linear-sram-for-ez80" class="button" target="_newWindow">
        BUY <img src="/logo-black.png" class="buy-on-shop"/>
      </a>
    </div>
  </div>
</div>

<hr/>

### 6 SLOT Green Backplane

<div class="tags">
  <div class="tag rcbus"></div>
  <div class="tag rc2014"></div>
  <div class="tag romwbw"></div>
</div>

Mount your Green Machine Modules in style, with this matching, colour coordinated backplane.

<div class="product-listing">
  <div>
    <a href="./green-6-slot-backplane"><img src="{{ site.baseurl }}/assets/green-6-slot-backplane/pcb-assembled-profile.jpg" alt="6 slot green backplane"></a>
  </div>
  <div>
    <p>A Small 6 slot 80 way backplane for Green Machine Modules and other compatible RC2014/RCBus modules</p>
    <p style="float: left"><a href="./green-6-slot-backplane">Click here for full details</a></p>
    <div class="buy-on-container">
      <a href="https://shop.dinoboards.com.au/product/6-slot-green-rcbus-backplane" class="button" target="_newWindow">
        BUY <img src="/logo-black.png" class="buy-on-shop"/>
      </a>
    </div>
  </div>
</div>

<hr/>

# Yellow MSX Series

These are a series of boards developed to achieve MSX+ compatibility.

The idea is that you can build each board one at a time, test it and play with it under RomWBW - and then once you have the set - load up some MSX games!

A working/bootable MSX system can be constructed in various configurations.  You can have all *Yellow* series modules, or use a mixture of Yellow and stock RC2014 modules.

For a bootable MSX system you need at least:

| Name | Options |
| ---- | --------|
| Backplane | The RC2014 Pro can work, although some signals will need to be connected via jumpers.  The Yellow 12+1 Backplane is recommended. |
| CPU  | The Yellow Turbo CPU module or a stock RC2014 Z80 and stock RC2014 Clock Module |
| Memory | The MSX Memory Module is required. |
| Keyboard | The PPI Module & Keyboard is required. |
| Video | The Yellow V99x8 MSX Video Module is required. |
| Sound | The Yellow YM2149 Game Module is required. |

<hr/>
### 12+1 Backplane

<div class="tags">
  <div class="tag rc2014"></div>
  <div class="tag msx recommended"></div>
</div>

<div class="product-listing">
  <div style="flex: 45%">
    <a href="./backplane"><img src="{{ site.baseurl }}/assets/backplane/profile-powered.jpg" alt="12+1 backplane powered"></a>
  </div>
  <div>
    <p>A Backplane for RC2014 systems, with 80 lanes, ideal for MSX configuration.</p>
    <p><a href="./backplane">Click here for full details</a></p>
    <div class="buy-on-container">
      <a href="https://shop.dinoboards.com.au/product/121-backplane-designed-for-rc2014-systems" class="button" target="_newWindow">
        BUY <img src="/logo-black.png" class="buy-on-shop"/>
      </a>
    </div>
  </div>
</div>

<hr/>
### MSX Cartridge Slot Extension for the 12+1 Backplane
<div class="tags">
  <div class="tag msx optional"></div>
  <div class="tag">12+1 Backplane required</div>
</div>
<div class="product-listing">
  <div>
    <a href="./slot-extension"><img src="{{ site.baseurl }}/assets/slot-extension/profile-powered.jpg" alt="Slot Extension"></a>
  </div>
  <div>
    <p>A extension module for RC2014 backplanes to support MSX Cartridges</p>
    <p><a href="./slot-extension">Click here for full details</a></p>
    <div class="buy-on-container">
      <a href="https://shop.dinoboards.com.au/product/msx-cartridge-slot-extension" class="button" target="_newWindow">
        BUY <img src="/logo-black.png" class="buy-on-shop"/>
      </a>
    </div>
  </div>
</div>

<hr/>
### MSX Cassette + USB Module

<div class="tags">
  <div class="tag rc2014"></div>
  <div class="tag romwbw">*</div>
  <div class="tag msx optional"></div>
  <div class="tag">* Only the USB module will work under RomWBW</div>
</div>

<div class="product-listing">
  <div>
    <a href="./cassette-and-usb"><img src="{{ site.baseurl }}/assets/cassette-and-usb/pcb-profile-usb-top.jpg" alt="Cassette + USB"></a>
  </div>
  <div>
    <p>Save your MSX-BASIC programs to cassette tape and give your Z80 access to a wide range of USB devices. (USB Module compatible with RomWBW)</p>
    <p><a href="./cassette-and-usb">Click here for full details</a></p>
    <div class="buy-on-container">
      <a href="https://shop.dinoboards.com.au/product/msx-cassette-usb-module-designed-for-rc2014" class="button" target="_newWindow">
        BUY <img src="/logo-black.png" class="buy-on-shop"/>
      </a>
    </div>
  </div>
</div>

<hr/>
### MSX Memory Module

<div class="tags">
  <div class="tag msx required"></div>
</div>

<div class="product-listing">
  <div>
    <a href="./msx-memory"><img src="{{ site.baseurl }}/assets/msx-memory/assembled.jpg" alt="MSX Memory Module"></a>
  </div>
  <div>
    <p>Give your RC2014 the power of 512K ROM and 1024K RAM.</p>
    <p><a href="./msx-memory">Click here for full details</a></p>
    <div class="buy-on-container">
      <a href="https://shop.dinoboards.com.au/product/msx-memory-board-for-rc2014" class="button" target="_newWindow">
        BUY <img src="/logo-black.png" class="buy-on-shop"/>
      </a>
    </div>
  </div>
</div>

<hr/>
### MSX PPI Module & Keyboard

<div class="tags">
  <div class="tag rc2014"></div>
  <div class="tag romwbw"></div>
  <div class="tag msx required"></div>
</div>

<div class="product-listing">
  <div>
    <a href="./ppi-and-keyboard"><img src="{{ site.baseurl }}/assets/ppi-and-keyboard/assembled-blue-caps-rainbow-connector.jpg" alt="PPI Module and keyboard"></a>
  </div>
  <div>
    <p>A full size keyboard kit for your RC2014 system, for use with 5 pin Cherry compatible switches.</p>
    <p><a href="./ppi-and-keyboard">Click here for full details</a></p>
    <div class="buy-on-container">
      <a href="https://shop.dinoboards.com.au/product/msx-keyboard-designed-for-rc2014" class="button" target="_newWindow">
        BUY <img src="/logo-black.png" class="buy-on-shop"/>
      </a>
    </div>
  </div>
</div>

<hr/>
### MSX Real-Time-Clock Module

<div class="tags">
  <div class="tag rc2014"></div>
  <div class="tag romwbw"></div>
  <div class="tag msx optional"></div>
</div>

<div class="product-listing">
  <div>
    <a href="./rtc-and-f4"><img src="{{ site.baseurl }}/assets/rtc-and-f4/assembled.jpg" alt="RP5C01 RTC and MSX F4"></a>
  </div>
  <div>
    <p>An MSX compatible Real time clock and MSX F4 Boot register.</p>
    <p><a href="./rtc-and-f4">Click here for full details</a></p>
    <div class="buy-on-container">
      <a href="https://shop.dinoboards.com.au/product/msx-rp5c01-rtc-and-msx-f4-board-for-rc2014" class="button" target="_newWindow">
        BUY <img src="/logo-black.png" class="buy-on-shop"/>
      </a>
    </div>
  </div>
</div>

<hr/>
### Turbo CPU

<div class="tags">
  <div class="tag rc2014"></div>
  <div class="tag romwbw"></div>
  <div class="tag msx optional"></div>
</div>

<div class="product-listing">
  <div>
    <a href="./turbo-cpu"><img src="{{ site.baseurl }}/assets/turbo-cpu/assembled-top.jpg" alt="Turbo CPU"></a>
  </div>
  <div>
    <p>A Z80 CPU module supporting speeds up to 20Mhz - but with the required wait states and clock control to ensure compatibility with existing software and RC2014 modules.</p>
    <p><a href="./turbo-cpu">Click here for full details</a></p>
    <div class="buy-on-container">
      <a href="https://shop.dinoboards.com.au/product/turbo-cpu-module-designed-for-rc2014" class="button" target="_newWindow">
        BUY <img src="/logo-black.png" class="buy-on-shop"/>
      </a>
    </div>
  </div>
</div>

<hr/>
### MSX V99x8 Video Module

<div class="tags">
  <div class="tag rc2014"></div>
  <div class="tag romwbw"></div>
  <div class="tag msx required"></div>
</div>

<div class="product-listing">
  <div>
    <a href="./video-v9958"><img src="{{ site.baseurl }}/assets/video-v9958/rgb-v3.8-profile.jpg" alt="Turbo CPU"></a>
  </div>
  <div>
    <p>Give your RC2014 the advanced graphic capabilities of the mid to late 80s. This kit is powered by a V9938 or V9958 Video Display Processors (VDP)</p>
    <p><a href="./video-v9958">Click here for full details</a></p>
    <div class="buy-on-container">
      <a href="https://shop.dinoboards.com.au/product/v99x8-msx-rgb-video-module-for-rc2014" class="button" target="_newWindow">
        BUY <img src="/logo-black.png" class="buy-on-shop"/>
      </a>
    </div>
  </div>
</div>

<hr/>
### MSX YM2149 Game Module

<div class="tags">
  <div class="tag rc2014"></div>
  <div class="tag romwbw"></div>
  <div class="tag msx required"></div>
</div>

<div class="product-listing">
  <div>
    <a href="./game"><img src="{{ site.baseurl }}/assets/game/installed.jpeg" alt="YM2149 Game Module"></a>
  </div>
  <div>
    <p>MSX compatible Sound and Game Controller Module</p>
    <p><a href="./game">Click here for full details</a></p>
    <div class="buy-on-container">
      <a href="https://shop.dinoboards.com.au/product/ym2149-msx-game-board-for-rc2014" class="button" target="_newWindow">
        BUY <img src="/logo-black.png" class="buy-on-shop"/>
      </a>
    </div>
  </div>
</div>

<hr/>
### MSX YM2413 Music Module

<div class="tags">
  <div class="tag msx optional"></div>
</div>

<div class="product-listing">
  <div>
    <a href="./music"><img src="{{ site.baseurl }}/assets/music/assembled-profile.jpg" alt="MSX YM2413 Music Module"></a>
  </div>
  <div>
    <p>Enhanced MSX+ sounds with the YM2413 (OPLL) sound chip.</p>
    <p><a href="./music">Click here for full details</a></p>
    <div class="buy-on-container">
      <a href="https://shop.dinoboards.com.au/product/ym2413-msx-music-module-designed-for-rc2014" class="button" target="_newWindow">
        BUY <img src="/logo-black.png" class="buy-on-shop"/>
      </a>
    </div>
  </div>
</div>
