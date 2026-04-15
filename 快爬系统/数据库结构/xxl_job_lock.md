---
created: 2026-04-15T10:54:54+08:00
modified: 2026-04-15T10:57:11+08:00
---
/*
 Navicat Premium Data Transfer

 Source Server         : Web-Clawer
 Source Server Type    : MySQL
 Source Server Version : 80045 (8.0.45)
 Source Host           : 101.42.47.30:3306
 Source Schema         : xxl-job

 Target Server Type    : MySQL
 Target Server Version : 80045 (8.0.45)
 File Encoding         : 65001

 Date: 15/04/2026 10:48:52
*/

SET NAMES utf8mb4;
SET FOREIGN_KEY_CHECKS = 0;

-- ----------------------------
-- Table structure for xxl_job_lock
-- ----------------------------
DROP TABLE IF EXISTS `xxl_job_lock`;
CREATE TABLE `xxl_job_lock`  (
  `lock_name` varchar(50) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci NOT NULL COMMENT '锁名称',
  PRIMARY KEY (`lock_name`) USING BTREE
) ENGINE = InnoDB CHARACTER SET = utf8mb4 COLLATE = utf8mb4_0900_ai_ci ROW_FORMAT = DYNAMIC;

SET FOREIGN_KEY_CHECKS = 1;
