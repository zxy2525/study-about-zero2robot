# 进入项目目录
cd /d/zero2robot_projects/zero2robot

# 查看当前目录，确认位置对不对
pwd
# 快速跑一遍（300步，最常用）
uv run python curriculum/phase0_foundations/ch0.1_sim_loop/sim_loop.py --smoke

# 完整跑一遍（2000步）
uv run python curriculum/phase0_foundations/ch0.1_sim_loop/sim_loop.py

# 打开回放窗口
uv run python -m rerun outputs/ch0.1-sim-loop/sim_loop.rrd

# 如果相对路径打不开，用绝对路径
uv run python -m rerun "$(pwd)/outputs/ch0.1-sim-loop/sim_loop.rrd"
# 1. 查看改了哪些文件
git status

# 2. 加入暂存区（只加一个文件）
git add curriculum/phase0_foundations/ch0.1_sim_loop/sim_loop.py

# 或加入所有改动
git add .

# 3. 提交到本地
git commit -m "说明这次改了什么"

# 4. 推送到 GitHub
git push
# 查看提交历史（一行一条）
git log --oneline

# 查看最近3条
git log --oneline -3

# 放弃某个文件的改动（还没 add）
git restore curriculum/phase0_foundations/ch0.1_sim_loop/sim_loop.py

# 放弃所有未提交的改动
git restore .

# 查看某个文件改了什么
git diff curriculum/phase0_foundations/ch0.1_sim_loop/sim_loop.py
# 安装依赖（只有改了 pyproject.toml 或新克隆项目时才需要）
uv sync

# 添加新依赖
uv add rerun-sdk

# 查看已安装的包
uv pip list

# 测试某个包是否可用
uv run python -c "import mujoco; print(mujoco.__version__)"