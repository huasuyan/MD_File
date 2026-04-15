---
created: 2026-04-15T10:58:51+08:00
modified: 2026-04-15T10:58:58+08:00
---
/*
 Navicat Premium Data Transfer

 Source Server         : Web-Clawer
 Source Server Type    : MySQL
 Source Server Version : 80045 (8.0.45)
 Source Host           : 101.42.47.30:3306
 Source Schema         : web_crawler

 Target Server Type    : MySQL
 Target Server Version : 80045 (8.0.45)
 File Encoding         : 65001

 Date: 15/04/2026 10:58:32
*/

SET NAMES utf8mb4;
SET FOREIGN_KEY_CHECKS = 0;

-- ----------------------------
-- Table structure for crawler
-- ----------------------------
DROP TABLE IF EXISTS `crawler`;
CREATE TABLE `crawler`  (
  `crawler_id` int NOT NULL AUTO_INCREMENT COMMENT '爬虫ID，主键自增',
  `crawler_name` varchar(50) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci NOT NULL COMMENT '爬虫名称，同一用户下唯一',
  `config_method` tinyint NOT NULL COMMENT '配置方式（0：脚本文件,1: 流程组件)',
  PRIMARY KEY (`crawler_id`) USING BTREE,
  INDEX `idx_user_name`(`crawler_name` ASC) USING BTREE
) ENGINE = InnoDB CHARACTER SET = utf8mb4 COLLATE = utf8mb4_unicode_ci COMMENT = '爬虫信息与配置表' ROW_FORMAT = DYNAMIC;

SET FOREIGN_KEY_CHECKS = 1;
