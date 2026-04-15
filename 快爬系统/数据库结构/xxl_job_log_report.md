---
created: 2026-04-15T10:55:05+08:00
modified: 2026-04-15T10:57:32+08:00
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

 Date: 15/04/2026 10:49:06
*/

SET NAMES utf8mb4;
SET FOREIGN_KEY_CHECKS = 0;

-- ----------------------------
-- Table structure for xxl_job_log_report
-- ----------------------------
DROP TABLE IF EXISTS `xxl_job_log_report`;
CREATE TABLE `xxl_job_log_report`  (
  `id` int NOT NULL AUTO_INCREMENT,
  `trigger_day` datetime NULL DEFAULT NULL COMMENT '调度-时间',
  `running_count` int NOT NULL DEFAULT 0 COMMENT '运行中-日志数量',
  `suc_count` int NOT NULL DEFAULT 0 COMMENT '执行成功-日志数量',
  `fail_count` int NOT NULL DEFAULT 0 COMMENT '执行失败-日志数量',
  `update_time` datetime NULL DEFAULT NULL,
  PRIMARY KEY (`id`) USING BTREE,
  UNIQUE INDEX `i_trigger_day`(`trigger_day` ASC) USING BTREE
) ENGINE = InnoDB AUTO_INCREMENT = 3917 CHARACTER SET = utf8mb4 COLLATE = utf8mb4_0900_ai_ci ROW_FORMAT = DYNAMIC;

SET FOREIGN_KEY_CHECKS = 1;
