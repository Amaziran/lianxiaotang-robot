# lianxiaotang-robot
这是一个基于openai-chatGPT的智能语音对话机器人，可以基于Linux和windows系统运行

感谢 潘伟洲 wukong-robot 语音机器人开源

credit by https://github.com/wzpan/wukong-robot


本项目基于wukong-robot进行了如下修改：
  1.使用腾讯云ASR服务（就目前看来免费额度完全能够支持日常使用）
  2.AI大模型接入OpenAI-chatGPT 4.1-nano
  3.解决了Console唤醒词模型与系统录音（唤醒后的提问词录制）冲突问题


Console唤醒词与系统录音冲突问题解决：

  在进行唤醒后的语音录制过程中发现系统录音无法正常访问媒体设备，警告信息为；设备或资源忙。原因是因为 PvRecorder.stop 和 PvRecorder.delete 并不能完全释放占用的媒体资源。
  
  解决方法：在唤醒词唤醒成功之后，问答语音录制前使用 sudo fuser -k /dev/snd/pcm* 指令进行媒体强制释放


文件目录：
  ~/.wukong         .wukong文件一般位于主文件夹
  
  ~/lianxiaotang-robot
