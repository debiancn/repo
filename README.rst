#############################
Debian 中文社区软件源
#############################

Debian 中文社区软件源使用说明
----------------------------------

Debian 中文社区提供了一系列软件，可作为对 Debian 官方仓库的一个补充，
其目的之一是改进 Debian 中文用户在 Debian 系统上的使用体验。

软件源地址：http://repo.debiancn.org

为维护简易起见，社区软件源暂时仅提供 amd64 架构的软件，且不提供源码包。
某些使用 Git 管理的软件可以在本仓库内找到对应的源代码。

要开始使用社区软件源，请遵照以下步骤进行操作，所有命令请使用超级用户权限执行：

Testing / Unstable 不稳定版用户
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

1. ``printf "deb [arch=amd64] http://repo.debiancn.org/ unstable main\ndeb [arch=amd64] http://repo.debiancn.org/ experimental main" > /etc/apt/sources.list.d/debiancn.list;``
2. ``wget http://repo.debiancn.org/pool/main/d/debiancn-keyring/debiancn-keyring_0~20160915_all.deb -O /tmp/debiancn-keyring.deb;``
3. ``apt install /tmp/debiancn-keyring.deb;``
4. ``apt update;``

这样将会启用社区源的 ``unstable`` 和 ``experimental`` 仓库，从而可以使用大多数社区源中的软件包。

Jessie 稳定版用户
~~~~~~~~~~~~~~~~~~

内容待添加……

彻底移除社区软件源
~~~~~~~~~~~~~~~~~~~~~~~

如果您需要彻底移除社区软件源，请按以下步骤操作：

1. ``apt purge debiancn-keyring;``
2. ``rm -f /etc/apt/sources.list.d/debiancn.list;``
3. ``apt update;``

Debian 中文社区软件源列表说明
-----------------------------------

这里列出社区软件源维护列表。使用 Git 管理的软件包打包脚本以子模块的形式给出。

软件包一览
------------------

* 无法从源代码构建的软件包
    - ``chrome``
    - ``wps-office``
    - ``visual-studio-code``
    - ``telegram-desktop``
    - ``netease-cloud-music``
    - ``haroopad`` ^
* 可以获得源代码但尚未使用 Git 管理的软件包
    - ``eric``
    - ``libpng12`` ^
    - ``deepin-menu``
    - ``xfce4-kbdleds-plugin`` ^
    - ``qtox`` ^
    - ``i3-gaps`` ^
* 使用 Git 管理的软件包
    - ``mini-buildd``
    - ``fortune-zh``
    - ``manpages-zh`` |travis-ci-package-manpages-zh|_
    - ``nixnote2``
    - ``deepin-terminal`` |travis-ci-package-deepin-terminal|_
    - ``goldendict``
    - ``krita`` (krita 3.x)
        + ``vc``
    - ``shadowsocks-qt5``
        + ``libqtshadowsocks``
    - ``cutegram``
        + ``libqtelegram-ae``
        + ``telegramqml``
        + ``asemantools``
    - ``obs-studio`` *

.. |travis-ci-package-manpages-zh| image:: https://travis-ci.org/debiancn/manpages-zh.svg?branch=debian
.. _travis-ci-package-manpages-zh: https://travis-ci.org/debiancn/manpages-zh
.. |travis-ci-package-deepin-terminal| image:: https://travis-ci.org/hosiet/deepin-terminal.svg?branch=master
.. _travis-ci-package-deepin-terminal: https://travis-ci.org/hosiet/deepin-terminal

.. *: 尚未作为子模块
.. ^: 尚未纳入管理

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

