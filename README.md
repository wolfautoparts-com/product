A custom module for [wolfautoparts.com](https://wolfautoparts.com) (Magento 2)  

## How to install
```
bin/magento maintenance:enable
rm -rf composer.lock
composer clear-cache
composer require wolfautoparts.com/product:*
bin/magento setup:upgrade
rm -rf var/di var/generation generated/code && bin/magento setup:di:compile
bin/magento cache:clean
rm -rf pub/static/*
bin/magento setup:static-content:deploy \
	--area adminhtml \
	--theme Magento/backend \
	-f en_US
bin/magento setup:static-content:deploy \
	--area frontend \
	--theme one80solution/wolfautoparts \
	-f en_US
bin/magento maintenance:disable
bin/magento cache:enable
```

## How to upgrade
```
bin/magento maintenance:enable
rm -rf composer.lock
composer clear-cache
composer update wolfautoparts.com/product
bin/magento setup:upgrade
rm -rf var/di var/generation generated/code && bin/magento setup:di:compile
bin/magento cache:clean
rm -rf pub/static/*
bin/magento setup:static-content:deploy \
	--area adminhtml \
	--theme Magento/backend \
	-f en_US
bin/magento setup:static-content:deploy \
	--area frontend \
	--theme one80solution/wolfautoparts \
	-f en_US
bin/magento maintenance:disable
bin/magento cache:enable
```

If you have problems with these commands, please check the [detailed instruction](https://mage2.pro/t/263).