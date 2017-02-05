#############################
Debian 中文社区软件源
#############################

Debian 中文社区软件源使用说明
----------------------------------

Debian 中文社区提供了一系列软件，可作为对 Debian 官方仓库的一个补充，
其目的之一是改进 Debian 中文用户在 Debian 系统上的使用体验。

软件源地址：https://repo.debiancn.org
软件源镜像站点请见 `Issue #60`_

.. _`Issue #60`: https://github.com/debiancn/repo/issues/60

为维护简易起见，社区软件源暂时仅提供 amd64 架构的软件。
有少部分软件同时提供源码包（使用 `deb-src` 启用）。
有极少量软件提供 i386 架构软件。
某些使用 Git 管理的软件可以在本仓库内找到对应的源代码。

要开始使用社区软件源，请遵照以下步骤进行操作，所有命令请使用超级用户权限执行：

启用社区源的命令
~~~~~~~~~~~~~~~~~~~
::

  sudo apt update;
  sudo apt install apt-transport-https;
  printf "deb https://repo.debiancn.org/ unstable main" > /etc/apt/sources.list.d/debiancn.list;
  wget https://repo.debiancn.org/pool/main/d/debiancn-keyring/debiancn-keyring_0~20161212_all.deb -O /tmp/debiancn-keyring.deb;
  apt install /tmp/debiancn-keyring.deb;
  apt update;


**注意** 以上命令适合``unstable/sid``用户。您可以自行替换``unstable``为您使用的发行代号。目前社区源可以使用以下代号：

* `unstable`, `sid` （效果相同）
* `testing`, `stretch` （stretch 发布以前效果相同）
* `jessie`, `stable` （stretch 发布以前效果相同）

彻底移除社区软件源
~~~~~~~~~~~~~~~~~~~~~~~

如果您需要彻底移除社区软件源，请按以下步骤操作：
::

  1. apt purge debiancn-keyring;
  2. rm -f /etc/apt/sources.list.d/debiancn.list;
  3. apt update;

Debian 中文社区软件源列表说明
-----------------------------------

这里列出社区软件源维护列表。使用 Git 管理的软件包打包脚本以子模块的形式给出。

软件包一览
------------------

.. list-table::
    :header-rows: 1
    
    * - **软件包名**
      - **软件全名**
      - **开源？**
      - **适合 Debian 版本**
      - **Git 管理？**
      - **持续集成**
      - **备注**
    * - debiancn-keyring
      - DebianCN Repo Keyring
      - 是
      - jessie, stretch, sid
      - 是
      - |travis-ci-package-debiancn-keyring|_
      -
    * - chrome
      - Google Chrome
      - 否
      - stretch, sid
      - N/A
      - N/A
      -
    * - chrome-remote-desktop
      - Chrome Remote Desktop
      - 否
      - stretch, sid
      - N/A
      - N/A
      -
    * - wps-office
      - Kingsoft WPS Office
      - 否
      - stretch, sid
      - N/A
      - N/A
      -
    * - sogoupinyin
      - Sogou Pinyin IM
      - 否
      - stretch, sid
      - N/A
      - N/A
      - 经过重新封包修改
    * - brackets
      - OSS Editor for web design
      - 是
      - stretch, sid
      - 否
      - N/A
      -
    * - bearychat
      - BearyChat working communicator
      - ?
      - stretch, sid
      - 否
      - N/A
      -
    * - atom
      - Atom Editor
      - 是
      - stretch, sid
      - 否
      - N/A
      -
    * - code
      - Visual Studio Code
      - 否
      - stretch, sid
      - N/A
      - N/A
      -
    * - sublime-text-dev
      - Sublime Text
      - 否
      - stretch, sid
      - N/A
      - N/A
      -
    * - snipaste
      - Snipping and Pasting tool
      - 否
      - stretch, sid
      - N/A
      - N/A
      -
    * - telegram
      - Telegram Desktop (Binary version)
      - 是
      - jessie, stretch, sid
      - 是
      - N/A
      -
    * - telegram-desktop
      - Telegram Desktop (built from source)
      - 是
      - stretch, sid
      - 是
      - N/A
      -
    * - netease-cloud-music
      - NetEase Cloud Music Client
      - 否
      - stretch, sid
      - N/A
      - N/A
      -
    * - skypeforlinux
      - Skype for Linux
      - 否
      - stretch, sid
      - N/A
      - N/A
      -
    * - oracle-java8-jdk
      - Oracle Java Development Kit
      - 否
      - stretch, sid
      - N/A
      - N/A
      -
    * - foxitreader
      - Foxit PDF Reader
      - 否
      - stretch, sid
      - N/A
      - N/A
      -
    * - haroopad
      - Haroopad Document Processor
      - 否
      - stretch, sid
      - N/A
      - N/A
      -
    * - deepin-menu
      - Deepin Menu Service
      - 是
      - stretch, sid
      - 是
      - N/A
      -
    * - deepin-gettext-tools
      - Deepin gettext wrapper
      - 是
      - stretch, sid
      - 是
      - N/A
      -
    * - deepin-tool-kit
      - Deepin Tool Kit
      - 是
      - stretch, sid
      - 是
      - N/A
      -
    * - deepin-qt5integration
      - Deepin Qt5 integration
      - 是
      - stretch, sid
      - 是
      - N/A
      -
    * - deepin-terminal
      - Deepin Terminal
      - 是
      - stretch, sid
      - 是
      - |travis-ci-package-deepin-terminal|_
      -
    * - pdnsd
      - Proxy DNS Server
      - 是
      - stretch, sid
      - 否
      - N/A
      -
    * - libpng12
      - PNG Library (v1.2)
      - 是
      - stretch, sid
      - 否
      - N/A
      - `libpng tracker <https://tracker.debian.org/pkg/libpng>`_; `RM <https://tracker.debian.org/news/768116>`_
    * - wine-staging
      - Wine Staging version
      - 是
      - sid
      - 是
      - N/A
      -
    * - wine-gecko-2.47
      - Wine Gecko Engine for wine 1.9.19+
      - 是
      - stretch, sid
      - 是
      - N/A
      -
    * - obs-studio
      - Open Broadcasting System
      - 是
      - jessie
      - 是
      - N/A
      - `obs tracker <https://tracker.debian.org/pkg/obs-studio>`_
    * - cutegram
      - Cutegram
      - 是
      - stretch, sid
      - 是
      - N/A
      -
    * - asemantools
      - Aseman Tools for Qt and Qml
      - 是
      - stretch, sid
      - 是
      - N/A
      -
    * - telegramqml
      - Telegram API Tools
      - 是
      - stretch, sid
      - 是
      - N/A
      -
    * - libqtelegram-ae
      - Libqtelegram Aseman Edition
      - 是
      - stretch, sid
      - 是
      - |travis-ci-package-libqtelegram-ae|_
      -
    * - shadowsocks-qt5
      - Shadowsocks client in Qt5
      - 是
      - jessie, stretch, sid
      - 是
      - N/A
      -
    * - libqtshadowsocks
      - libqtshadowsocks
      - 是
      - jessie, stretch, sid
      - 是
      - N/A
      -
    * - goldendict
      - Goldendict (Qt5 version)
      - 是
      - stretch, sid
      - 是
      - N/A
      - `goldendict tracker <https://tracker.debian.org/pkg/goldendict>`_
    * - vc
      - VC C++ library
      - 是
      - stretch, sid
      - 是
      - N/A
      - `ubuntu <https://packages.ubuntu.com/source/yakkety/vc>`_
    * - vi
      - Traditional Vi
      - 是
      - stretch, sid
      - 是
      - N/A
      -
    * - qtox
      - QTox
      - 是
      - stretch, sid
      - 否
      - N/A
      -
    * - i3-gaps
      - i3 Unofficial Fork
      - 是
      - stretch, sid
      - 否
      - N/A
      -
    * - xfce4-kbdleds-plugin
      - Xfce panel keyboard LEDs plugin
      - 是
      - stretch, sid
      - 否
      - N/A
      -


.. |travis-ci-package-deepin-terminal| image:: https://travis-ci.org/hosiet/deepin-terminal.svg?branch=master
.. _travis-ci-package-deepin-terminal: https://travis-ci.org/hosiet/deepin-terminal
.. |travis-ci-package-debiancn-keyring| image:: https://travis-ci.org/debiancn/debiancn-keyring.svg?branch=master
.. _travis-ci-package-debiancn-keyring: https://travis-ci.org/debiancn/debiancn-keyring
.. |travis-ci-package-libqtelegram-ae| image:: https://travis-ci.org/debiancn/libqtelegram-aseman-edition.svg?branch=master
.. _travis-ci-package-libqtelegram-ae: https://travis-ci.org/debiancn/libqtelegram-aseman-edition

向社区源提交一个软件包
------------------------------------

如果您发现了一个适合 Debian 但无法向官方源提交的软件，您可以考虑将其加入我们的社区软件源。

* 如果这个软件是闭源软件，请直接在 issue 中提交信息并附带 ``.deb`` 包下载链接；
* 如果这个软件是开源软件，推荐使用 Git 管理打包内容 [#Git1]_ 并在 issue 中附上相关信息。其打包 Git 仓库将作为 repo 项目的子项目并在 repo 项目更新时触发自动打包。

.. [#Git1] 您可以参考本项目内的各个软件的打包实例，或者访问 https://anonscm.debian.org/git/ 页面参考官方所有使用 Git 管理打包的源代码仓库。

缩略词解释
-----------------

提交 issue 中的大多数缩略词来源于 `Debian WNPP`_ 和 `Debian ftp-master`_ 的请求类型。

.. _`Debian WNPP`: https://www.debian.org/devel/wnpp
.. _`Debian ftp-master`: https://ftp-master.debian.org/removals.html

+----------+---------------------------+--------------------------------------+
| 缩略词   | 完整意义                  | 解释                                 |
+==========+===========================+======================================+
|ITP       | Intent To Package         | 准备接手打包某个软件                 |
+----------+---------------------------+--------------------------------------+
|RFS [#F1]_| Request For Sponsorship   | 打包工作已完成，请求检查与上传       |
+----------+---------------------------+--------------------------------------+
|RFP       | Request For Package       | 请求他人对某个软件进行打包           |
+----------+---------------------------+--------------------------------------+
|RFH       | Request For Help          | 某个软件的打包者遇到技术困难请求协助 |
+----------+---------------------------+--------------------------------------+
|O         | Orphaned                  | 打包/维护者声明放弃维护，请求接手    |
+----------+---------------------------+--------------------------------------+
|RM        | Remove                    | 请求删除某个软件包                   |
+----------+---------------------------+--------------------------------------+
|RFU [#F2]_| Request For Update/Upgrade| 请求更新某个软件包                   |
+----------+---------------------------+--------------------------------------+

.. [#F1] 仅适用于没有上传帐号的用户。如果拥有上传帐号，通常可以直接进行上传。
.. [#F2] 不属于 Debian 官方使用的请求。

