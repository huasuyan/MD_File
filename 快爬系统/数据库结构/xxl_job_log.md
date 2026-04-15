---
created: 2026-04-15T10:54:59+08:00
modified: 2026-04-15T10:57:22+08:00
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

 Date: 15/04/2026 10:49:00
*/

SET NAMES utf8mb4;
SET FOREIGN_KEY_CHECKS = 0;

-- ----------------------------
-- Table structure for xxl_job_log
-- ----------------------------
DROP TABLE IF EXISTS `xxl_job_log`;
CREATE TABLE `xxl_job_log`  (
  `id` bigint NOT NULL AUTO_INCREMENT,
  `job_group` int NOT NULL COMMENT '执行器主键ID',
  `job_id` int NOT NULL COMMENT '任务，主键ID',
  `executor_address` varchar(255) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci NULL DEFAULT NULL COMMENT '执行器地址，本次执行的地址',
  `executor_handler` varchar(255) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci NULL DEFAULT NULL COMMENT '任务handler',
  `executor_param` text CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci NULL COMMENT '任务参数',
  `executor_sharding_param` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci NULL DEFAULT NULL COMMENT '任务分片参数，格式如 1/2',
  `executor_fail_retry_count` int NOT NULL DEFAULT 0 COMMENT '失败重试次数',
  `trigger_time` datetime NULL DEFAULT NULL COMMENT '调度-时间',
  `trigger_code` int NOT NULL COMMENT '调度-结果',
  `trigger_msg` text CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci NULL COMMENT '调度-日志',
  `handle_time` datetime NULL DEFAULT NULL COMMENT '执行-时间',
  `handle_code` int NOT NULL COMMENT '执行-状态',
  `handle_msg` text CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci NULL COMMENT '执行-日志',
  `alarm_status` tinyint NOT NULL DEFAULT 0 COMMENT '告警状态：0-默认、1-无需告警、2-告警成功、3-告警失败',
  PRIMARY KEY (`id`) USING BTREE,
  INDEX `I_trigger_time`(`trigger_time` ASC) USING BTREE,
  INDEX `I_handle_code`(`handle_code` ASC) USING BTREE,
  INDEX `I_jobgroup`(`job_group` ASC) USING BTREE,
  INDEX `I_jobid`(`job_id` ASC) USING BTREE
) ENGINE = InnoDB AUTO_INCREMENT = 1297 CHARACTER SET = utf8mb4 COLLATE = utf8mb4_0900_ai_ci ROW_FORMAT = DYNAMIC;

SET FOREIGN_KEY_CHECKS = 1;
