# Git Setup Config

## git 配置文件
 1. linux: ~/.gitconfig
 2. windows: C:\Users\$USER

## 制定配置文件目录
 1. git config -f <file>

## 配置用户信息[Your Identity]
 1. git config --global user.name "jasperlee"
 2. git config --global user.email "jasper_china@live.cn"

## 配置指定编辑器打开冲突
 1. linux: git config --global core.editor vim
 2. windows git config --global core.editor "'C:/xx.exe' -multiInst -nosession" 

## 查看用户配置
 1. git config --list

## 查看某一项用户配置
 1. git config user.name