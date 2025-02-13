# todo_app
class Todo
  def initialize
    @tasks = []
   menu
  end
  def menu
    loop do
      puts "----------------"
      puts "選択してください"
      puts "1:タスクの追加" 
      puts "2:タスクの表示"
      puts "3:タスクの消去"
      puts "4:終了"
      puts "----------------"

      @input = gets.chomp.to_i
      case @input
      when 1
        add
      when 2
        display
      when 3
        erase
      when 4
        puts "終了します"
        break
      end
    end
  end

  def add
    puts "タスクを入力してください"
    @task = gets.chomp
    @tasks << @task
  end

  def display
    if @tasks.empty?
      puts "タスクはありません"
    else
    @tasks.each_with_index do |task , index|
      puts "#{index + 1} : #{task}" 
    end
  end

  def erase
    display
    puts "どれを消去しますか？"
    @del = gets.chomp.to_i - 1
    @tasks.delete_at(@del)
    puts "タスクが消去されました"

  end
end

todo = Todo.new

end
