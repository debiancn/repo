#############################
Debian 中文社区软件源
#############################

Debian 中文社区软件源使用说明
----------------------------------

Debian 中文社区提供了一系列软件，可作为对 Debian 官方仓库的一个补充，
其目的之一是改进 Debian 中文用户在 Debian 系统上的使用体验。

软件源地址：https://repo.debiancn.org （仅IPv4）
软件源镜像站点请见 `Issue #60`_ （含IPv6支持）

.. _`Issue #60`: https://github.com/debiancn/repo/issues/60

为维护简易起见，社区软件源暂时优先提供 ``amd64`` 架构的软件。
有少部分软件同时提供源码包（使用 ``deb-src`` 启用）。
少量软件提供 ``i386`` 架构。
如果您没有找到所需的架构，请在 issue 中提交请求，志愿者将尽量满足需求。
某些使用 Git 管理的软件可以在本仓库内找到对应的源代码。

要开始使用社区软件源，请遵照以下步骤进行操作：

启用社区源的命令
~~~~~~~~~~~~~~~~~~~
.. code:: bash

  echo "deb https://repo.debiancn.org/ testing main" | sudo tee /etc/apt/sources.list.d/debiancn.list;
  wget https://repo.debiancn.org/pool/main/d/debiancn-keyring/debiancn-keyring_0~20161212_all.deb -O /tmp/debiancn-keyring.deb;
  sudo apt install /tmp/debiancn-keyring.deb;
  sudo apt update;
  rm /tmp/debiancn-keyring.deb;

**注意：** 以上命令适合 ``testing/buster`` 用户。您可以自行替换 ``testing`` 为您使用的发行代号。目前社区源可以使用以下代号：

* ``unstable``, ``sid`` （效果相同，实际指向 ``testing``）
* ``testing``, ``buster`` （``buster`` 发布以前效果相同）
* ``stretch``, ``stable`` （``buster`` 发布以前效果相同）
* ``jessie``, ``oldstable`` （``buster`` 发布以前效果相同）

使用 ``stretch`` 及以下版本，需安装 ``apt-transport-https``，``testing`` 及以上版本不需要。命令如下：

.. code:: bash

  sudo apt update;
  sudo apt install apt-transport-https;

目前暂无专用于 ``sid`` 的仓库，实际指向 ``testing``。若发行代号填写 ``unstable`` 或 ``sid``，可能会遇到以下错误：

::

  W: 冲突的发行版：https://repo.debiancn.org unstable InRelease (期望 unstable 但得到 buster)

将发行代号改为 ``testing`` 或 ``buster`` 即可。

彻底移除社区软件源
~~~~~~~~~~~~~~~~~~~~~~~

如果您需要彻底移除社区软件源，请按以下步骤操作：

.. code:: bash

  sudo apt purge debiancn-keyring;
  sudo rm -f /etc/apt/sources.list.d/debiancn.list;
  sudo apt update;

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
    * - google-chrome-stable
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
    * - gifski
      - GIF encoder based on libimagequant
      - 是
      - buster
      - 是
      - N/A
      -
    * - winetricks-zh
      - Winetricks for Chinese software
      - 是
      - stretch, buster
      - 是
      - N/A
      -
    * - wps-office
      - Kingsoft WPS Office
      - 否
      - stretch, sid
      - N/A
      - N/A
      -
    * - lilydict
      - lilydict online directory
      - 是
      - stretch, buster
      - 是
      - N/A
      -
    * - bcloud
      - Baidu Yun Client
      - 是
      - jessie, stretch
      - 是
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
      - Editor for web design
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
    * - latte-dock
      - Dock based on plasma frameworks
      - 是
      - sid
      - 是
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
      - 是
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
    * - electronic-wechat
      - WeChat client for macOS and Linux
      - 是
      - stretch, sid
      - N/A
      - N/A
      - 采用上游binary版本
    * - fgrun
      - Flightgear Launch Control
      - 是
      - stretch
      - N/A
      - N/A
      - `Tracker <https://tracker.debian.org/pkg/fgrun>`_
    * - unzip-iconv
      - Unzip CLI tool with iconv support
      - 是
      - stretch, sid
      - 否
      - N/A
      -
    * - netease-cloud-music
      - NetEase Cloud Music Client
      - 否
      - stretch, buster
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
    * - scp-foundation-doc-cn
      - the SCP Foundation document (CN Branch)
      - 是
      - stretch, sid
      - 是
      - N/A
      -
    * - rsync-huai
      - Rsync with huai extension
      - 是
      - jessie, stretch
      - 是
      - N/A
      -
    * - deepin-menu
      - Deepin Menu Service
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
      - stretch
      - 是
      - |travis-ci-package-deepin-terminal|_
      -
    * - ttyd
      - Web terminal sharing tool
      - 是
      - stretch, sid
      - 是
      - N/A
      -
    * - jieba
      - Jieba Chinese text segmentation library
      - 是
      - jessie
      - 是
      - N/A
      -
    * - vocal
      - Simple podcast client for the modern desktop
      - 是
      - stretch, sid
      - 是
      - N/A
      -
    * - python-xpybutil
      - Abstraction over X Python Binding
      - 是
      - stretch, sid
      - 是
      - N/A
      -
    * - python3-dae
      - Deepin App Engine
      - 是
      - stretch, sid
      - 是
      - N/A
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
    * - vc
      - VC C++ library
      - 是
      - stretch
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
    * - master-pdf-editor
      - Multifunctional PDF Editor
      - 否
      - stretch, buster
      - 否
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
* 如果这个软件是开源软件，推荐使用 Git 管理打包内容 [#Git1]_ 并在 issue 中附上相关信息。其打包 Git 仓库将作为 repo 项目的子项目。自动打包功能尚未完成。

有服务器帐号的用户，请将 ``.deb`` 二进制包或 ``.dsc`` 源码包使用 SFTP 上传至服务器，服务器将定时处理上传队列：

* ``scp ./mypackage.deb myusername@hz1.debiancn.org:/srv/repo/upload/target_codename/``

将其中的 ``target_codename`` 替换为目标版本代号（jessie, stretch, buster）。unstable 与 buster 共用仓库。

.. [#Git1] 您可以参考本项目内的各个软件的打包实例，或者访问 https://salsa.debian.org/ 页面参考官方所有使用 Git 管理打包的源代码仓库。

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

